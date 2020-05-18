<template>
    <div id="app">
        <Header/>
        <Slider/>
        <BottomMenu/>
        <Catalog/>
    </div>
</template>

<script>
    import 'bootstrap/dist/css/bootstrap.css'
    import 'bootstrap-vue/dist/bootstrap-vue.css'

    export default {
        name: 'App',
        /**
         * Пример динамического импорта компонентов:
         * */
        components: {
            Header: () => import(/* webpackChunkName: "header" */ './components/Header'),
            Slider: () => import(/* webpackChunkName: "header" */ './components/Slider'),
            BottomMenu: () => import(/* webpackChunkName: "header" */ './components/BottomMenu'),
            Catalog: () => import(/* webpackChunkName: "header" */ './components/Catalog'),
        }
    }
</script>

<style lang="scss">
    @font-face {
        font-family: 'Yanone Kaffeesatz';
        src: local('Yanone Kaffeesatz Extra Light'),
        local('YanoneKaffeesatz-ExtraLight'),
        url('assets/fontYanone/yanonekaffeesatzextralight.woff2') format('woff2'),
        url('assets/fontYanone/yanonekaffeesatzextralight.woff') format('woff'),
        url('assets/fontYanone/yanonekaffeesatzextralight.ttf') format('truetype');
        font-weight: 200;
        font-style: normal;
    }

    @font-face {
        font-family: 'Yanone Kaffeesatz';
        src: local('Yanone Kaffeesatz Light'),
        local('YanoneKaffeesatz-Light'),
        url('assets/fontYanone/yanonekaffeesatzlight.woff2') format('woff2'),
        url('assets/fontYanone/yanonekaffeesatzlight.woff') format('woff'),
        url('assets/fontYanone/yanonekaffeesatzlight.ttf') format('truetype');
        font-weight: 300;
        font-style: normal;
    }

    @font-face {
        font-family: 'Yanone Kaffeesatz';
        src: local('Yanone Kaffeesatz'),
        local('YanoneKaffeesatz-Regular'),
        url('assets/fontYanone/yanonekaffeesatz.woff2') format('woff2'),
        url('assets/fontYanone/yanonekaffeesatz.woff') format('woff'),
        url('assets/fontYanone/yanonekaffeesatz.ttf') format('truetype');
        font-weight: 400;
        font-style: normal;
    }

    @font-face {
        font-family: 'Yanone Kaffeesatz';
        src: local('Yanone Kaffeesatz Bold'),
        local('YanoneKaffeesatz-Bold'),
        url('assets/fontYanone/yanonekaffeesatzbold.woff2') format('woff2'),
        url('assets/fontYanone/yanonekaffeesatzbold.woff') format('woff'),
        url('assets/fontYanone/yanonekaffeesatzbold.ttf') format('truetype');
        font-weight: 700;
        font-style: normal;
    }

    #app {
        font-family: 'Yanone Kaffeesatz', serif;

        .container-fluid {
            padding: 0 100px 0 100px;

            .container {
                max-width: 100%;
                padding: 0;
            }
        }
    }

    @media (max-width: 1200px) {
        #app {
            .container-fluid {
                padding: 0 15px 0 15px;
            }
        }
    }
</style>
