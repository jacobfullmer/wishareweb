<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <div class="profile">
        <h1 class="theme--dark">This is a profile page</h1>
        <h2> HELLO</h2>
        <v-layout row wrap justify-left>
            <v-dialog v-model="dialog" max-width="290">
                <template v-slot:activator="{ on }">
                    <v-btn dark v-on="on" flat
                           class="themegreen--text"
                            @click.stop="dialog = true">Button</v-btn>
                </template>
                <v-card class="themedark darken-1">
                    <v-card-title class="headline">You clicked the button</v-card-title>
                    <v-card-text>Thank you for clicking the button.</v-card-text>
                    <v-card-actions>
                        <v-btn color="green darken-1" flat @click="dialog = false">Cancel</v-btn>
                        <v-btn color="green darken-1" flat @click="dialog = false">Download</v-btn>
                    </v-card-actions>
                </v-card>
            </v-dialog>
        </v-layout>
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

<style scoped>

</style>