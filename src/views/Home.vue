<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <div class="home" style="background-color: #4c4c4c">
        <div class="logo" style="padding-top: 100px; width: 100%; align-content: center;">
            <v-img src="https://i.imgur.com/OXlMnRp.png" style="max-height: 100px; max-width: 100px; display: block; margin: 0 auto"></v-img>
        </div>
        <div style="padding-top: 10px; width: 100%; align-content: center">
            <p class="display-3 themegreen--text" style="margin: 0 auto; text-align: center">Welcome to WiShare</p>
        </div>
        <div style="padding-top: 10px; width: 100%; align-content: center">
            <p class="headline themedark-text darken-2" style="margin: 0 auto; text-align: center">We're here to make WiFi easier</p>
        </div>
        <v-layout row wrap justify-center>
            <v-dialog v-model="dialog" max-width="290">
                <template v-slot:activator="{ on }">
                    <v-btn dark v-on="on" flat class="themegreen--text">Download now</v-btn>
                </template>
                <v-card class="themedark darken-1">
                    <v-card-title class="headline">WiShare is an Android application</v-card-title>
                    <v-card-text>You can download WiShare from the Google play store.</v-card-text>
                    <v-card-actions>
                        <v-spacer></v-spacer>
                        <v-btn color="green darken-1" flat @click="dialog = false">Cancel</v-btn>
                        <v-btn color="green darken-1" flat @click="dialog = false">Download</v-btn>
                    </v-card-actions>
                </v-card>
            </v-dialog>
        </v-layout>
        <v-container fill-height grid-list-md npmtext-xs-center>
            <v-layout  style="width: 100%" class="justify-self-center; themedark darken-1">
                <v-flex fill-height>
                    <v-card height="100%" style="width: fit-content; margin: auto">
                        <v-card-media class="justify-center">
                            <v-parallax style="width: 250px;" src="https://i.imgur.com/UV4p6NI.png"> </v-parallax>
                        </v-card-media>
                    </v-card>
                </v-flex>
                <v-flex fill-height justify-content-center>
                    <v-card height="100%" style="width: fit-content; margin: auto" class="justify-self-center">
                        <v-card-media class="justify-content-center">
                            <v-parallax style="width: 250px; justify-content: center" src="https://i.imgur.com/Aqbsddx.png"> </v-parallax>
                        </v-card-media>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>
    </div>
</template>

<script>
    export default {
        name: "Profile",
        data() {
            return {
                dialog: false
            }
        }
    }
</script>