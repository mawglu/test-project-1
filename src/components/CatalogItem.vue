<template>
    <div class="product-wrap">
        <img :src="img" :alt="name">
        <div class="product-actions">
            <div class="flag">
                <img :src="flagByCountry">
            </div>
            <div class="tag">
                {{tag}}
            </div>
        </div>
        <div class="product-info">
            <div class="title">
                {{name}}
                <div class="sub-title">
                    {{description}}
                </div>
            </div>
            <div class="product-bottom">
                <div class="sizes">
                    <b-button v-for="size in sizesActivity" :key="JSON.stringify(size)" @click="sizeClick(size.val)" :class="{'active' : size.active}">
                        {{ size.val }}
                    </b-button>
                    <div>размер</div>
                </div>
                <div class="price">
                    <span class="sale">{{priceOld}}</span>
                    <span>{{price}}</span>
                </div>
                <a href="#" class="basket"/>
            </div>
        </div>
        <div class="actions">
            <div class="action-table">
                <div v-for="prop in properties" :key="prop.propName">{{prop.propName}}</div>
                <div v-for="prop in properties" :key="prop.propVal">{{prop.propVal}}</div>
            </div>
            <a href="#">Перейти в карточку</a>
        </div>
    </div>
</template>

<script>
    import 'typeface-clear-sans'

    export default {
        name: "CatalogItem",
        data() {
            return {
                sizesActivity: [
                    {
                        val: '44',
                        active: true,
                    },
                    {
                        val: '46',
                        active: false,
                    },
                ]
            }
        },
        props: {
            id: {
                type: Number,
                default: 0
            },
            img: {
                type: String,
                default: ''
            },
            country: {
                type: String,
                default: '',
                validator: function (value) {
                    // Значение должно соответствовать одной из этих строк
                    let usedCountries = [
                        'fr',
                        'en'
                    ];
                    return usedCountries.indexOf(value) !== -1
                }
            },
            tag: {
                type: String,
                default: ''
            },
            name: {
                type: String,
                default: ''
            },
            description: {
                type: String,
                default: ''
            },
            sizes: {
                type: Array,
                default() {
                    return ['42', '44', '46', '48']
                }
            },
            priceOld: {
                type: String,
                default: '790 р.'
            },
            price: {
                type: String,
                default: ''
            },
            itemPage: {
                type: String,
                default: ''
            },
            properties: {
                type: Array,
                default() {
                    return [{
                        propName: 'Материал',
                        propVal: 'Хлопок'
                    }]
                }
            },
        },
        computed: {
            flagByCountry() {
                let path = '/img/flag1.svg';

                switch (this.country) {
                    case 'fr':
                        path = '/img/flag1.svg';
                        break;
                    case 'en':
                        path = '/img/flag2.svg';
                        break;
                    default:
                        path = '';
                        break;
                }
                return path;
            }
        },
        methods: {
            sizeClick: function (size) {
                for (let i = 0; i < this.sizesActivity.length; i++) {
                    this.sizesActivity[i].active = this.sizesActivity[i].val === size;
                }

                this.active = !this.active;
            }
        },
        mounted() {
            this.sizesActivity = [];

            for (let i = 0; i < this.sizes.length; i++) {
                this.sizesActivity.push({
                    val: this.sizes[i],
                    active: (i === 0)
                });
            }
        }
    }
</script>

<style scoped lang="scss">
    .product-wrap {
        display: flex;
        flex-direction: column;
        position: relative;
        margin: 10px;
        @media screen and (max-width: 414px) {
            margin: 5px;
        }

        img {
            max-width: 100%;
            height: auto;
        }

        .product-actions {
            font-family: 'Clear Sans', sans-serif;
            position: absolute;
            z-index: 3;
            top: 0;
            left: 0;
            padding: 50px 20px;

            .flag {
                max-width: 16px;
                max-height: 15px;
                margin: 0 0 20px 0;

                img {
                    width: 100%;
                    height: auto;
                    margin: 0;
                }
            }

            .tag {
                border-radius: 4px;
                background-color: rgb(0, 0, 0);
                font-size: 14px;
                color: rgb(255, 255, 255);
                font-weight: bold;
                line-height: 1.2;
                padding: 1px 10px;
            }
        }

        @media screen and (max-width: 1000px) {
            .product-actions {
                padding: 20px 10px;

                .flag {
                    margin: 0 0 10px 0;
                }

                .tag {
                    border-radius: 4px;
                    background-color: rgb(0, 0, 0);
                    font-size: 14px;
                    color: rgb(255, 255, 255);
                    font-weight: bold;
                    line-height: 1.2;
                    padding: 1px 10px;
                }
            }
        }

        .product-info {
            margin: 25px 0 25px 0;
            display: flex;
            flex-direction: column;
            font-family: 'Yanone Kaffeesatz', serif;
            position: relative;
            z-index: 3;

            .title {
                font-size: 24px;
                color: rgb(0, 0, 0);
                font-weight: bold;
                line-height: 1.2;

                .sub-title {
                    font-size: 16px;
                    font-weight: normal;
                    font-family: 'Clear Sans', sans-serif;
                    color: rgb(0, 0, 0);
                    line-height: 1.2;
                    margin: 10px 0 0 0;
                }
            }

            @media screen and (max-width: 1000px) {
                .title {
                    font-size: 18px;

                    .sub-title {
                        font-size: 14px;
                    }
                }
            }

            .product-bottom {
                display: flex;
                flex-direction: row;
                justify-content: space-between;

                .sizes {
                    margin: 8px 0 0 0;

                    div {
                        display: block;
                        width: 100%;
                        margin: 10px 0 0 0;
                        font-size: 18px;
                        color: rgb(0, 0, 0);
                        text-transform: uppercase;
                        line-height: 1.2;
                    }

                    button {
                        font-size: 16px;
                        font-family: 'Clear Sans', sans-serif;
                        color: rgb(186, 186, 186);
                        font-weight: bold;
                        line-height: 1.2;
                        border: 1px solid rgb(186, 186, 186);
                        background: transparent;
                        border-radius: 4px;
                        padding: 0 13px;
                        display: inline-block;
                        margin: 0 5px 0 0;
                        outline: none;

                        &.active {
                            color: rgb(239, 127, 26);
                            border: 1px solid rgb(239, 127, 26);
                        }

                        &:hover {
                            color: rgb(239, 127, 26);
                            border: 1px solid rgb(239, 127, 26);
                        }
                    }
                }

                .price {
                    position: relative;
                    margin: auto 0 0 auto;

                    span {
                        font-size: 36px;
                        color: rgb(0, 0, 0);
                        font-weight: bold;
                        line-height: 1.2;

                        &.sale {
                            font-size: 24px;
                            color: rgb(187, 187, 187);
                            font-weight: normal;
                            text-decoration: line-through;
                            line-height: 1.2;
                            position: absolute;
                            top: -40%;
                            left: 0;
                        }
                    }
                }

                .basket {
                    display: block;
                    width: 24px;
                    height: 22px;
                    background: url("/img/basket-or.svg") no-repeat center;
                    background-size: contain;
                    cursor: pointer;
                    margin: auto 20px auto 10px;
                }

                @media screen and (max-width: 1000px) {
                    .sizes {
                        margin: 5px 0 0 0;

                        div {
                            font-size: 16px;
                        }

                        span {
                            font-size: 14px;
                            padding: 0 10px;
                        }
                    }

                    .price {
                        position: relative;
                        margin: auto 0 0 auto;

                        span {
                            font-size: 20px;

                            &.sale {
                                font-size: 14px;
                            }
                        }
                    }
                }
            }
        }

        .actions {
            font-family: 'Clear Sans', sans-serif;
            position: absolute;
            top: -10px;
            left: -10px;
            background-color: rgb(0, 0, 0, 0.8);
            padding: 0 15px 0 15px;
            width: calc(100% + 20px);
            height: calc(100% + 20px);
            display: flex;
            flex-direction: column;

            opacity: 0;
            transition: .5s ease-in-out;

            .action-table {
                border-top: 1px solid rgb(255, 255, 255);
                border-right: 1px solid rgb(255, 255, 255);
                border-left: 1px solid rgb(255, 255, 255);
                display: flex;
                flex-wrap: wrap;
                margin: 45% auto 15% auto;

                div {
                    font-size: 16px;
                    line-height: normal;
                    width: 50%;
                    padding: 8px 10px 15px 10px;
                    border-bottom: 1px solid rgb(255, 255, 255);

                    &:nth-child(odd) {
                        color: rgb(172, 172, 172);
                        text-align: left;
                        border-right: 1px solid rgb(255, 255, 255);
                    }

                    &:nth-child(even) {
                        color: rgb(255, 255, 255);
                        text-align: right;
                    }
                }
            }

            a {
                font-size: 16px;
                color: rgb(239, 127, 26);
                font-weight: bold;
                text-decoration: underline;
                line-height: 1.2;
                text-align: center;
            }

            @media screen and (max-width: 1000px) {
                .action-table {
                    div {
                        font-size: 12px;
                        padding: 5px;
                    }
                }

                a {
                    font-size: 14px;
                }
            }
        }

        &:hover {
            .product-info {
                .title {
                    color: rgb(255, 255, 255);

                    .sub-title {
                        color: rgb(255, 255, 255);
                    }
                }

                .product-bottom {

                    .sizes {
                        div {
                            color: rgb(255, 255, 255);
                        }
                    }

                    .price {

                        span {
                            color: rgb(255, 255, 255);
                        }
                    }
                }
            }

            .actions {
                opacity: 1;
            }
        }
    }
</style>