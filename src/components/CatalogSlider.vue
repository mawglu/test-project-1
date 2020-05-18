<template>
    <Carousel :autoplay="false"
              :nav="true"
              :nav-text="navText"
              :items="2"
              :loop="true"
              :responsive="{
                  1112: {
                      items:4,
                      dots: false
                  },
                  700: {
                      items:3,
                      dots: false
                  },
                  414: {
                      items:2,
                      dots: false,
                      center: true
                  },
                  0: {
                      items:1,
                      dots: false,
                      center: true,
                  }
              }"
    >
        <CatalogItem :key="item.id" v-for="item in catalogItems" v-bind="item"/>
    </Carousel>
</template>

<script>
    export default {
        name: "CatalogSlider",
        components: {
            CatalogItem: () => import(/* webpackChunkName: "catalog-item" */ './../components/CatalogItem'),
            Carousel: () => import(/* webpackChunkName: "owl-carousel" */ 'vue-owl-carousel'),
        },
        data() {
            return {
                navText: ['<img src="/img/prev.png"/>', '<img src="/img/next.png"/>'],
                catalogItems: [
                    {
                        id: 1,
                        img: '/img/catalog1.png',
                        country: 'fr',
                        tag: 'new',
                        name: 'Кожаная юбка',
                        description: 'Описание: Полосатая кофта из полосатого трикотажа, без молнии',
                        sizes: [44],
                        priceOld: '',
                        price: '790 р.',
                        itemPage: '',
                        properties: [
                            {
                                propName: 'Материал',
                                propVal: 'Хлопок',
                            },
                            {
                                propName: 'Сезон',
                                propVal: 'Лето',
                            },
                            {
                                propName: 'Страна-производитель',
                                propVal: 'Франция',
                            },
                            {
                                propName: 'Длина',
                                propVal: 'Мини',
                            }
                        ]
                    },
                    {
                        id: 2,
                        img: '/img/catalog2.png',
                        country: 'en',
                        tag: 'sale',
                        name: 'Платье в горох с поясом',
                        description: 'Описание: Полосатая кофта из полосатого трикотажа, без молнии',
                        sizes: [44, 46, 48],
                        priceOld: '1190 р.',
                        price: '790 р.',
                        itemPage: '',
                        properties: [
                            {
                                propName: 'Материал',
                                propVal: 'Хлопок',
                            },
                            {
                                propName: 'Сезон',
                                propVal: 'Лето',
                            },
                            {
                                propName: 'Страна-производитель',
                                propVal: 'Франция',
                            },
                            {
                                propName: 'Длина',
                                propVal: 'Мини',
                            }
                        ]
                    },
                    {
                        id: 3,
                        img: '/img/catalog3.png',
                        country: 'fr',
                        tag: 'new',
                        name: 'Розовое платье',
                        description: 'Описание: Полосатая кофта из полосатого трикотажа, без молнии',
                        sizes: [44, 46, 48],
                        priceOld: '',
                        price: '790 р.',
                        itemPage: '',
                        properties: [
                            {
                                propName: 'Материал',
                                propVal: 'Хлопок',
                            },
                            {
                                propName: 'Сезон',
                                propVal: 'Лето',
                            },
                            {
                                propName: 'Страна-производитель',
                                propVal: 'Франция',
                            },
                            {
                                propName: 'Длина',
                                propVal: 'Мини',
                            }
                        ]
                    },
                    {
                        id: 4,
                        img: '/img/catalog4.png',
                        country: 'fr',
                        tag: 'new',
                        name: 'Полосатая кофта',
                        description: 'Описание: Полосатая кофта из полосатого трикотажа, без молнии',
                        sizes: [44],
                        priceOld: '',
                        price: '790 р.',
                        itemPage: '',
                        properties: [
                            {
                                propName: 'Материал',
                                propVal: 'Хлопок',
                            },
                            {
                                propName: 'Сезон',
                                propVal: 'Лето',
                            },
                            {
                                propName: 'Страна-производитель',
                                propVal: 'Франция',
                            },
                            {
                                propName: 'Длина',
                                propVal: 'Мини',
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>
<style lang="scss">
    .root-tabs-content {
        margin: 0 -10px 0 -10px;

        .owl-carousel {
            .owl-nav {
                display: block;
                position: absolute;
                top: -50px;
                right: 10px;

                &.disabled {
                    display: block;
                }

                .owl-prev,
                .owl-next {
                    padding: 0;
                    margin: 0;
                    background: transparent;
                    border-radius: 0;

                    &:hover {
                        background: transparent;
                    }
                }

                .owl-prev {
                    margin: 0 35px 0 0;
                }
            }
        }
    }
</style>
