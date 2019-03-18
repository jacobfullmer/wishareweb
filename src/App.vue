<template>

    <v-app style="background-color: #4c4c4c">
        <Navbar></Navbar>
        <v-content>
            <router-view></router-view>
        </v-content>
        <Footer></Footer>
    </v-app>

</template>

<script>

    import Navbar from './components/Navbar'
    import Footer from './components/Footer'

    export default {

        components: {Navbar,
                     Footer},
        name: 'App',
        data() {
            return {}
        }

    }


</script>