<template>
    <div class="catalog">
        <b-container fluid>
            <b-container>
                <b-row>
                    <b-col>
                        <b-tabs content-class="root-tabs-content">
                            <b-tab title="Лучшие предложения недели" active>
                                <div>
                                    <CatalogSlider/>
                                </div>
                            </b-tab>
                            <b-tab title="Новинки">
                                <CatalogSlider/>
                            </b-tab>
                            <b-tab title="Рекомендуем">
                                <CatalogSlider/>
                            </b-tab>
                        </b-tabs>
                    </b-col>
                </b-row>
            </b-container>
        </b-container>
    </div>
</template>

<script>
    export default {
        name: "Catalog",
        components: {
            CatalogSlider: () => import(/* webpackChunkName: "header" */ './../components/CatalogSlider'),
        },
    }
</script>

<style lang="scss">
    .catalog {
        padding: 55px 0 70px 0;
        @media screen and (max-width: 1000px) {
            padding: 25px 0 50px 0;
        }

        .nav-tabs {
            border-bottom: none;

            .nav-item {
                margin: 0 60px 0 0;

                .nav-link {
                    border: none;
                    font-size: 36px;
                    color: rgb(0, 0, 0);
                    line-height: 1.2;
                    padding: 0;
                    outline: none;

                    &.active {
                        color: rgb(239, 127, 26);
                        border-bottom: 2px solid rgb(239, 127, 26);
                    }
                }
            }

            @media screen and (max-width: 1000px) {
                .nav-item {
                    margin: 0 30px 0 0;

                    .nav-link {
                        font-size: 18px;

                        &.active {
                            border-bottom: 1px solid rgb(239, 127, 26);
                        }
                    }
                }
            }
            @media screen and (max-width: 414px) {
                .nav-item {
                    margin: 0 15px 0 0;

                    .nav-link {
                        font-size: 14px;
                    }
                }
            }
        }

        .root-tabs-content {
            padding: 25px 0 0 0;
        }

        @media screen and (max-width: 1000px) {
            .root-tabs-content {
                padding: 15px 0 0 0;
            }
        }
        @media screen and (max-width: 414px) {
            .root-tabs-content {
                padding: 50px 0 0 0;
            }
        }
    }
</style>
