<template>
    <header>
        <b-container fluid>
            <b-container>
                <b-navbar toggleable="lg">
                    <b-navbar-toggle target="nav-collapse"/>
                    <b-collapse id="nav-collapse" is-nav>
                        <b-navbar-nav>
                            <b-nav-item active href="#">Каталог</b-nav-item>
                            <b-nav-item href="#">Компания</b-nav-item>
                            <b-nav-item href="#">Новости</b-nav-item>
                            <b-navbar-brand href="/">
                                <img src="/img/Monoteka.png">
                            </b-navbar-brand>
                            <b-nav-item href="#">Поставщикам</b-nav-item>
                            <b-nav-item href="#">Контакты</b-nav-item>
                            <b-nav-item href="#">Кабинет</b-nav-item>
                            <b-nav-item>
                                <b-nav-form>
                                    <b-form-input class="search-input" :class="{isActive}"/>
                                    <b-button class="search" type="submit" @click="SearchFade"/>
                                </b-nav-form>
                            </b-nav-item>
                            <b-nav-item href="#" class="basket"/>
                        </b-navbar-nav>
                    </b-collapse>
                </b-navbar>
            </b-container>
        </b-container>
    </header>
</template>

<script>
    export default {
        name: "Header",
        data() {
            return {
                isActive: false,
            }
        },
        methods: {
            SearchFade: function () {
                this.isActive = !this.isActive;
            }
        }
    }
</script>

<style scoped lang="scss">
    .navbar {
        padding: 20px 0;

        .navbar-nav {
            width: 100%;
            justify-content: space-between;

            .navbar-brand {
                padding: 0;
                font-size: 0;
                line-height: normal;
                margin: auto;
            }

            @media screen and (max-width: 834px) {
                width: 50%;
                margin: 20px 0 0 0;
                .navbar-brand {
                    margin: 15px 0;
                }
            }

            .nav-item {
                margin: auto 3% auto 0;

                &:last-child {
                    margin: auto 0;
                }

                @media screen and (max-width: 1400px) {
                    margin: auto 0 auto 0;
                }

                .nav-link {
                    font-size: 24px;
                    line-height: 1.2;
                    color: rgb(0, 0, 0);
                    text-transform: uppercase;

                    &.active {
                        padding: 9px 80px 10px 25px;
                        background-color: rgb(239, 127, 26);
                        position: relative;
                        font-size: 18px;
                        color: rgb(254, 254, 254);

                        &:before {
                            content: '';
                            background: url("/img/active.png") no-repeat center;
                            width: 10px;
                            height: 17px;
                            position: absolute;
                            right: 17px;
                            top: 11px;
                        }
                    }
                }

                @media screen and (max-width: 834px) {
                    order: 2;
                    .nav-link {
                        font-size: 16px;

                        &.active {
                            padding: 6px 80px 8px 10px;
                            font-size: 16px;
                        }
                    }
                }
            }
        }


        .search-input {
            opacity: 0;
            border-radius: 25px;
            position: absolute;
            right: 0;
            outline: none;
            bottom: -20%;
            z-index: 2;
            transition: all .5s;

            &.isActive {
                opacity: 1;
            }

            &:focus {
                outline: none;
                box-shadow: none;
                border-color: #ef7f1a;
            }
        }

        .search {
            width: 19px;
            height: 19px;
            background: url("/img/search.svg") no-repeat center;
            border: none;
            border-radius: 0;
            outline: none;
            margin: auto 0 auto 0;
        }

        .basket {
            width: 24px;
            height: 22px;
            background: url("/img/basket.svg") no-repeat center;
            border: none;
            border-radius: 0;
            outline: none;
            margin: auto 0 auto 0;
        }
    }


</style>