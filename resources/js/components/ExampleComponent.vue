<template>
    <v-app id="inspire">
        <v-content>
            <v-container fluid fill-height>
                <v-layout align-center justify-center>
                    <v-flex xs12 sm8 md4>
                        <v-card class="elevation-12">
                            <v-toolbar dark color="primary">
                                <v-toolbar-title>Login form</v-toolbar-title>
                            </v-toolbar>
                            <v-card-text>
                                <v-form>
                                    <v-text-field
                                        name="Email"
                                        label="Email"
                                        type="text"
                                    ></v-text-field>
                                    <v-text-field
                                        name="Password"
                                        label="Password"
                                        type="password"
                                    ></v-text-field>
                                </v-form>
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer></v-spacer>
                                <v-btn color="primary" to="/">Login</v-btn>
                            </v-card-actions>
                        </v-card>
                    </v-flex>
                </v-layout>
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        },
        data () {
            return {
                valid: false,
                e1: false,
                password: '',
                passwordRules: [
                    (v) => !!v || 'Password is required',
                ],
                email: '',
                emailRules: [
                    (v) => !!v || 'E-mail is required',
                    (v) => /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
                ],
            }
        },
        methods: {
            submit () {
                if (this.$refs.form.validate()) {
                    this.$refs.form.$el.submit()
                }
            },
            clear () {
                this.$refs.form.reset()
            }
        },
    }
</script>
