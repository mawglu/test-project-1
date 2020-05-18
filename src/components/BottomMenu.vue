<template>
    <b-container fluid class="bottom-menu">
        <b-row>
            <b-col cols="6" md="4" lg="2" class="menu-item">
                <a href="/">
                    <img src="/img/menu1.svg">
                    <div class="title">платья</div>
                </a>
            </b-col>
            <b-col cols="6" md="4" lg="2" class="menu-item">
                <a href="/">
                    <img src="/img/menu2.svg">
                    <div class="title">шубы</div>
                </a>
            </b-col>
            <b-col cols="6" md="4" lg="2" class="menu-item">
                <a href="/">
                    <img src="/img/menu3.svg">
                    <div class="title">пиджаки</div>
                </a>
            </b-col>
            <b-col cols="6" md="4" lg="2" class="menu-item">
                <a href="/">
                    <img src="/img/menu4.svg">
                    <div class="title">блузки</div>
                </a>
            </b-col>
            <b-col cols="6" md="4" lg="2" class="menu-item">
                <a href="/">
                    <img src="/img/menu5.svg">
                    <div class="title">джинсы</div>
                </a>
            </b-col>
            <b-col cols="6" md="4" lg="2" class="menu-item">
                <a href="/">
                    <img src="/img/menu6.svg">
                    <div class="title">рубашки</div>
                </a>
            </b-col>
        </b-row>
    </b-container>
</template>

<script>
    export default {
        name: "BottomMenu"
    }
</script>

<style scoped lang="scss">
    .bottom-menu {
        .menu-item {
            padding: 0;

            a {
                display: flex;
                flex-direction: column;
                background: black;
                border: 0.5px solid white;
                padding: 10px 10px 15px 10px;
                max-height: 100px;
                height: 100px;
                text-decoration: none;

                img {
                    max-width: 100%;
                    height: auto;
                    margin: 0 auto 5px auto;
                }

                .title {
                    font-size: 24px;
                    color: rgb(255, 255, 255);
                    text-transform: uppercase;
                    line-height: 1.2;
                    text-align: center;
                    margin: auto 0 0 0;
                }
            }

            @media screen and (max-width: 414px) {
                a {
                    .title {
                        font-size: 16px;
                    }
                }
            }

            &:first-child,
            &:nth-child(6n+1) {
                padding: 0 0 0 16px;
            }

            &:nth-child(6n) {
                padding: 0 16px 0 0;
            }


            @media screen and (max-width: 1000px) {

                &:nth-child(3n) {
                    padding: 0 16px 0 0;
                }

                &:nth-child(3n+1) {
                    padding: 0 0 0 16px;
                }
            }
            @media screen and (max-width: 767px) {
                &:nth-child(odd) {
                    padding: 0 0 0 16px;
                }
                &:nth-child(even) {
                    padding: 0 16px 0 0;
                }
            }
        }
    }

</style>