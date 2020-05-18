<template>
    <div class="banner-wrap">
        <b-container fluid>
            <b-container>
                <b-row>
                    <b-col cols="12" lg="8" md="6" class="pr-lg-0 pr-md-0 pr-3">
                        <div class="banner-carousel banner-item">
                            <b-carousel
                                    id="banner"
                                    v-model="slide"
                                    :interval="5000000"
                                    controls
                                    img-width="1024"
                                    img-height="480"
                            >
                                <b-carousel-slide img-src="/img/slide1.png">
                                    <div class="banner-title">
                                        Monoteka-group — лучшие моменты
                                        жизни вместе с нашими платьями!
                                    </div>
                                    <b-button class="btn banner-btn">
                                        купить
                                    </b-button>
                                </b-carousel-slide>
                                <b-carousel-slide img-src="/img/slide1.png">
                                    <div class="banner-title">
                                        Monoteka-group — лучшие моменты
                                        жизни вместе с нашими платьями!
                                    </div>
                                </b-carousel-slide>
                                <b-carousel-slide img-src="/img/slide1.png">
                                    <div class="banner-title">
                                        Monoteka-group — лучшие моменты
                                        жизни вместе с нашими платьями!
                                    </div>
                                    <b-button class="btn banner-btn">
                                        купить
                                    </b-button>
                                </b-carousel-slide>
                            </b-carousel>
                        </div>
                    </b-col>
                    <b-col cols="6" lg="2" md="3" class="px-lg-0 px-md-0 pr-0">
                        <div class="banner-item banner-xs"
                             style="background: url('/img/banner-1.png') no-repeat center top / contain">
                            <div class="card-img-overlay">
                                <div class="card-title">Пиджаки</div>
                                <div class="card-text">
                                    <a href="#">
                                        в наших магазинах
                                    </a>
                                </div>
                            </div>
                        </div>
                    </b-col>
                    <b-col cols="6" lg="2" md="3" class="pl-lg-0 pl-md-0 pl-0 pr-md-3">
                        <div class="banner-item banner-xs"
                             style="background: url('/img/banner-2.png') no-repeat center top / cover">
                            <div class="card-img-overlay">
                                <div class="card-title">Деловой стиль</div>
                                <div class="card-text">
                                    <a href="#">
                                        узнать больше
                                    </a>
                                </div>
                            </div>
                        </div>
                    </b-col>
                </b-row>
            </b-container>
        </b-container>
    </div>
</template>
<script>
    export default {
        name: "Slider",
        data() {
            return {
                slide: 0,
                sliding: null,
            }
        },
    }
</script>


<style lang="scss">
    .banner-wrap {
        .banner-carousel {
            position: relative;

            &:before {
                content: '';
                width: 100%;
                height: 100%;
                position: absolute;
                top: 0;
                left: 0;
                background: linear-gradient(90deg, rgb(0, 0, 0) 0%, rgba(0, 0, 0, 0) 100%);
                opacity: 0.8;
                z-index: 5;
            }

            .carousel-caption {
                bottom: 60px;
                z-index: 10;

                .banner-title {
                    font-size: 48px;
                    color: rgb(255, 255, 255);
                    font-weight: bold;
                    line-height: 1.2;
                    text-align: left;
                    max-width: 570px;
                }

                .banner-btn {
                    font-size: 18px;
                    color: rgb(255, 255, 255);
                    text-transform: uppercase;
                    line-height: 1.2;
                    text-align: center;

                    border: 3px solid rgb(242, 242, 242);
                    background-color: rgb(239, 127, 26);
                    border-radius: 0;
                    width: 154px;
                    height: 40px;
                    outline: none;
                    display: block;
                    margin: 45px 0 auto 0;
                }
            }


            .carousel-control-next,
            .carousel-control-prev {
                opacity: 1;
                transition: all .5s;
                z-index: 15;

                &:hover {
                    opacity: 0.5;
                }

                .carousel-control-next-icon,
                .carousel-control-prev-icon {
                    background-image: url("/img/banner-arrow.png");
                    background-size: contain;
                    width: 50px;
                    height: 50px;
                    border-radius: 50%;
                }
            }

            .carousel-control-prev {
                transform: rotate(180deg);
            }

            @media screen and (max-width: 1024px) {
                .carousel-caption {
                    bottom: 50px;

                    .banner-title {
                        font-size: 35px;
                        max-width: 535px;
                    }

                    .banner-btn {
                        margin: 25px 0 auto 0;
                    }
                }
            }

            @media screen and (max-width: 1000px) {
                .carousel-caption {
                    bottom: 20px;

                    .banner-title {
                        font-size: 18px;
                        max-width: 100%;
                    }

                    .banner-btn {
                        font-size: 16px;
                        width: 130px;
                        height: 35px;
                        margin: 15px 0 auto 0;
                    }
                }
                .carousel-control-next,
                .carousel-control-prev {

                    .carousel-control-next-icon,
                    .carousel-control-prev-icon {
                        width: 20px;
                        height: 20px;
                    }
                }
            }

            @media screen and (max-width: 767px) {
                .carousel-caption {
                    bottom: 30%;
                }
            }

            @media screen and (max-width: 320px) {
                .carousel-caption {
                    bottom: 0;

                    .banner-title {
                        font-size: 16px;
                    }

                    .banner-btn {
                        font-size: 11px;
                        width: 80px;
                        height: 30px;
                        margin: 10px 0 auto 0;
                    }
                }
            }
        }


        .banner-item {
            height: 100%;
            border-radius: 0;
            border: 0.5px solid white;
            position: relative;

            &:before {
                content: '';
                width: 100%;
                height: 100%;
                position: absolute;
                top: 0;
                left: 0;
                background: linear-gradient(0deg, rgb(0, 0, 0) 0%, rgba(0, 0, 0, 0) 100%);
                opacity: 0.702;
            }

            @media screen and (max-width: 1000px) {
                background-size: cover !important;
            }


            .card-img-overlay {
                display: flex;
                flex-direction: column;
                padding: 15px 15px 30px 15px;

                .card-title {
                    font-size: 30px;
                    color: rgb(255, 255, 255);
                    font-weight: bold;
                    line-height: 1.2;
                    margin: auto auto 15px auto;
                }

                .card-text {
                    font-size: 16px;
                    color: rgb(239, 127, 26);
                    font-weight: bold;
                    text-decoration: underline;
                    line-height: 1.2;
                    text-align: center;

                    a {
                        color: rgb(239, 127, 26);
                    }
                }
            }

            &.banner-xs {
                @media screen and (max-width: 767px) {
                    background: black !important;
                    padding: 30px 15px 65px 15px;
                    .card-img-overlay {
                        display: flex;
                        flex-direction: column;
                        padding: 15px 15px 30px 15px;
                    }
                }
            }

            @media screen and (max-width: 1024px) {
                .card-img-overlay {
                    display: flex;
                    flex-direction: column;
                    padding: 15px 15px 30px 15px;

                    .card-title {
                        font-size: 24px;
                    }
                }
            }
        }

    }
</style>