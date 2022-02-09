<template>
<div>
    <v-container>
        <v-row class="mb-5" justify="center">
            <v-form ref="form" lazy-validation v-model="valid">
                <v-text-field :counter="10" :rules="nameRules" required v-model="name" label="name"></v-text-field>
                <v-text-field :rules="emailRules" required v-model="email" label="email"></v-text-field>
                <v-text-field :rules="passwordRules" required v-model="password" type="password" label="password"></v-text-field>
                <v-select :rules="selectRules" :items="items" v-model="select" label="item" required></v-select>
                <v-checkbox :rules="checkRules" required label="Do you agree" v-model="checkbox"></v-checkbox>
                <v-btn :disabled="!valid" class="mr-4" @click="validate" color="success">Validate</v-btn>
                <v-btn class="mr-4" @click="reset" color="eror">Reset form</v-btn>
                <v-btn class="mr-4" @click="resetValidate" color="warning">Reset Validate</v-btn>
            </v-form>
        </v-row>
        <template>
            <v-stepper v-model="e6" vertical>
                <v-stepper-step :complete="e6 > 1" step="1">
                    Select an app
                    <small>Summarize if needed</small>
                </v-stepper-step>

                <v-stepper-content step="1">
                    <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
                    <v-btn color="primary" @click="e6 = 2">
                        Continue
                    </v-btn>
                    <v-btn text>
                        Cancel
                    </v-btn>
                </v-stepper-content>

                <v-stepper-step :complete="e6 > 2" step="2">
                    Configure analytics for this app
                </v-stepper-step>

                <v-stepper-content step="2">
                    <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
                    <v-btn color="primary" @click="e6 = 3">
                        Continue
                    </v-btn>
                    <v-btn text>
                        Cancel
                    </v-btn>
                </v-stepper-content>

                <v-stepper-step :complete="e6 > 3" step="3">
                    Select an ad format and name ad unit
                </v-stepper-step>

                <v-stepper-content step="3">
                    <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
                    <v-btn color="primary" @click="e6 = 4">
                        Continue
                    </v-btn>
                    <v-btn text>
                        Cancel
                    </v-btn>
                </v-stepper-content>

                <v-stepper-step step="4">
                    View setup instructions
                </v-stepper-step>
                <v-stepper-content step="4">
                    <v-card color="grey lighten-1" class="mb-12" height="200px"></v-card>
                    <v-btn color="primary" @click="e6 = 1">
                        Continue
                    </v-btn>
                    <v-btn text>
                        Cancel
                    </v-btn>
                </v-stepper-content>
            </v-stepper>
        </template>
        <template>
            <v-row>
                <v-col cols="12" sm="6" offset-sm="3">
                    <v-card>
                        <v-toolbar color="white" flat>
                            <v-btn icon light>
                                <v-icon color="grey darken-2">
                                    mdi-arrow-left
                                </v-icon>
                            </v-btn>

                            <v-toolbar-title class="grey--text text--darken-4">
                                Albums
                            </v-toolbar-title>

                            <v-spacer></v-spacer>

                            <v-btn icon light>
                                <v-icon color="grey darken-2">
                                    mdi-magnify
                                </v-icon>
                            </v-btn>
                        </v-toolbar>

                        <v-subheader>May</v-subheader>
                        <v-container fluid>
                            <v-row>
                                <v-col v-for="i in 6" :key="i" cols="4">
                                    <img :src="`https://randomuser.me/api/portraits/men/${i + 20}.jpg`" alt="lorem" class="image" height="100%" width="100%">
                                </v-col>
                            </v-row>
                        </v-container>

                        <v-subheader>June</v-subheader>
                        <v-container fluid>
                            <v-row>
                                <v-col v-for="i in 6" :key="i" cols="4">
                                    <img :src="`https://randomuser.me/api/portraits/women/${i + 5}.jpg`" alt="lorem" class="image" height="100%" width="100%">
                                </v-col>
                            </v-row>
                        </v-container>

                        <v-footer class="mt-12"></v-footer>
                    </v-card>
                </v-col>
            </v-row>
        </template>
        <template>
            <v-treeview :items="itemss"></v-treeview>
        </template>
    </v-container>
</div>
</template>

<script>
export default {
    name: 'Form',
    data() {
        return {
            e6: 1,
            valid: true,

            name: '',
            nameRules: [
                v => !!v || 'name is required',
                v => (v && v.length <= 10) || 'number must be less than 10 chracters'
            ],
            email: '',
            emailRules: [
                v => !!v || 'email is required',
                v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
            ],
            select: null,
            selectRules: [v => !!v || 'item  is required'],
            checkRules: [v => !!v || 'you must agree to continue'],
            items: ['app', 'web', 'graphics', 'data structure'],
            password: '',
            passwordRules: [
                v => !!v || 'password is required',
                v => (v && v.length <= 8) || 'password must be less than 10 chracters'
            ],
            checkbox: false,
            itemss: [{
                    id: 1,
                    name: 'Applications :',
                    children: [{
                            id: 2,
                            name: 'Calendar : app'
                        },
                        {
                            id: 3,
                            name: 'Chrome : app'
                        },
                        {
                            id: 4,
                            name: 'Webstorm : app'
                        },
                    ],
                },
                {
                    id: 5,
                    name: 'Documents :',
                    children: [{
                            id: 6,
                            name: 'vuetify :',
                            children: [{
                                id: 7,
                                name: 'src :',
                                children: [{
                                        id: 8,
                                        name: 'index : ts'
                                    },
                                    {
                                        id: 9,
                                        name: 'bootstrap : ts'
                                    },
                                ],
                            }, ],
                        },
                        {
                            id: 10,
                            name: 'material2 :',
                            children: [{
                                id: 11,
                                name: 'src :',
                                children: [{
                                        id: 12,
                                        name: 'v-btn : ts'
                                    },
                                    {
                                        id: 13,
                                        name: 'v-card : ts'
                                    },
                                    {
                                        id: 14,
                                        name: 'v-window : ts'
                                    },
                                ],
                            }, ],
                        },
                    ],
                },
                {
                    id: 15,
                    name: 'Downloads :',
                    children: [{
                            id: 16,
                            name: 'October : pdf'
                        },
                        {
                            id: 17,
                            name: 'November : pdf'
                        },
                        {
                            id: 18,
                            name: 'Tutorial : html'
                        },
                    ],
                },
                {
                    id: 19,
                    name: 'Videos :',
                    children: [{
                            id: 20,
                            name: 'Tutorials :',
                            children: [{
                                    id: 21,
                                    name: 'Basic layouts : mp4'
                                },
                                {
                                    id: 22,
                                    name: 'Advanced techniques : mp4'
                                },
                                {
                                    id: 23,
                                    name: 'All about app : dir'
                                },
                            ],
                        },
                        {
                            id: 24,
                            name: 'Intro : mov'
                        },
                        {
                            id: 25,
                            name: 'Conference introduction : avi'
                        },
                    ],
                },
            ],
        }
    },
    methods: {
        validate() {
            this.$refs.form.validate()
        },
        reset() {
            this.$refs.form.reset()
        },
        resetValidate() {
            this.$refs.form.resetValidate()
        }
    }
}
</script>

<style lang="scss" scoped>

</style>
