<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
    <nav>
        <v-toolbar app class="themedark darken-2">
            <v-toolbar-side-icon @click="drawer = !drawer" class="themegreen--text"></v-toolbar-side-icon>
            <v-toolbar-title class="themegreen--text">
                <span class="font-weight-light">Wi</span>
                <span>Share</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
                <v-dialog v-model="dialog" id="dialog" width="80%">
                    <template v-slot:activator="{on}">
                        <v-btn id="navBarButton" flat color="themegreen"
                               @click="navbarButtonClick">
                            <span>{{label}}</span>
                            <v-icon right>{{navbarBtnIcon}}</v-icon>
                        </v-btn>
                        <v-layout style="display: none">
                            <v-select v-model="logout" v-if="showDropDown" @input="selected" style="width: 1%"
                                      color="themegreen" lable="select" :items="options" required></v-select>
                        </v-layout>
                    </template>
                    <v-card class="themedark darken-1">
                        <v-card-title>
                            <span class="headline">Sign up</span>
                        </v-card-title>
                        <v-card-text>
                            <v-container grid-list-md>
                                <v-layout wrap>
                                    <v-flex xs12 sm6 md4>
                                        <v-text-field v-model="firstName" name="firstName"
                                                      color="themegreen" label="First name*"
                                                      input type="text" required>{{firstName}}</v-text-field>
                                    </v-flex>
                                    <v-flex xs12 sm6 md4>
                                        <v-text-field v-model="middleName" name="middleName"
                                                      color="themegreen" input type="text"
                                                      label="Middle name">{{middleName}}</v-text-field>
                                    </v-flex>
                                    <v-flex xs12 sm6 md4>
                                        <v-text-field v-model="lastName" name="lastName"
                                                      color="themegreen" label="Last name*"
                                                      input type="text" required>{{lastName}}</v-text-field>
                                    </v-flex>
                                    <v-flex xs12 background-color="themedark">
                                        <v-text-field v-model="email" name="email"
                                                      color="themegreen" label="Email*"
                                                      input type="email" required>{{email}}</v-text-field>
                                    </v-flex>
                                    <v-flex xs12>
                                        <v-text-field v-model="password" name="password"
                                                      color="themegreen" label="Password*"
                                                      input type="password" required>{{password}}</v-text-field>
                                    </v-flex>
                                </v-layout>
                            </v-container>
                            <small style="padding-left: 22px">*indicates required field</small>
                        </v-card-text>
                        <v-card-actions>
                            <v-spacer></v-spacer>
                            <v-btn class="themegreen--text" flat @click="dialog = false">Close</v-btn>
                            <v-btn class="themegreen--text" flat @click="processForm">Submit</v-btn>
                        </v-card-actions>
                    </v-card>
                </v-dialog>
        </v-toolbar>

        <v-navigation-drawer temporary v-model="drawer" app class="themegreen">
            <v-list>
                <v-list-tile v-for="link in links" :key="link.text" router :to="link.route" active-class="white--text">
                    <v-list-tile-action>
                        <v-icon class="themedark-text darken-2">{{link.icon}}</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-content>
                        <v-list-tile-title class="themedark-text darken-2">{{link.text}}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>

    </nav>
</template>

<script>
    export default {
        name: "Navbar",
        data() {
            return {
                dialog: false,
                logout: false,
                drawer: false,
                links: [
                    {icon: 'home', text: 'Home', route: '/wishareweb'},
                    {icon: 'help', text: 'About', route: '/about'},
                    // {icon: 'person', text: 'Profile', route: '/profile'},
                ],
                options: [
                    {text: 'Logout'}
                ],
                showDropDown: false,
                label: 'Sign up',
                navbarBtnIcon: 'exit_to_app',
                firstName: '',
                middleName: '',
                lastName: '',
                email: '',
                password: '',
                autocomplete: null
            }
        },
        methods: {
            navbarButtonClick: function() {
              if(!this.showDropDown)  {
                  this.dialog = true;
              } else {
                  // var dropDown = document.getElementById("dropDownMenu");
                  // dropDown.enable();
                  //
                  this.label = "Sign up";
                  this.navbarBtnIcon = 'exit_to_app';
                  this.showDropDown = false;
              }
            },

            processForm: function() {
                const firstName = this.firstName;
                const lastName = this.lastName;
                this.label = "Welcome, " + firstName + " " + lastName;
                this.navbarBtnIcon = 'arrow_drop_down';
                this.showDropDown = true;
                this.dialog = false;
            },

            selected: function() {
                this.label = "Sign up";
                this.navbarBtnIcon = 'exit_to_app';
                this.showDropDown = false;
            }
        }
    }
</script>

<style scoped>

</style>