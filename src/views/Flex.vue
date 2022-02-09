<template>
<div>
    <v-flex>

        <div class="d-flex  flex-wrap   justify-space-around   ">
            <div class="box text-justify overflow-auto">
                <h1>Overflow</h1> Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae quaerat repellat quae nisi illum recusandae totam nam, maxime eaque quidem quia magni rem inventore dolorum ratione! Libero eius cumque exercitationem?
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eius debitis, quas unde fugit facere veritatis deserunt libero neque eum autem totam maxime expedita quidem pariatur assumenda dolorem repudiandae! Pariatur, impedit?
                Lorem ipsum dolor sit, amet consectetur adipisicing elit. A laborum sunt, repudiandae quis deleniti unde autem ad, illo libero voluptatum velit ratione dolor cum eos sint, quae porro aspernatur vitae!
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Soluta dolorum exercitationem ducimus. Minima ipsam nam possimus earum voluptates unde similique, tenetur, deserunt reprehenderit dolore laboriosam iste magnam esse. Laudantium, aliquid.
            </div>
            <div class="box">2
                <v-alert border="bottom" color="white" icon="mdi-account" outlined text type="success">phulra</v-alert>
            </div>
            <div class="box">3
                <template>
                    <div class="text-center">
                        <v-avatar color="blue">
                            <v-icon dark>
                                mdi-alarm
                            </v-icon>
                        </v-avatar>
                    </div>
                </template> </div>
            <div class="box">
                <v-container>
                    <v-row align="center" justify="center">
                        <v-badge bordered color="error" icon="mdi-twitter" overlap>
                            <v-btn class="white--text" color="blue" depressed>
                                Lock Account
                            </v-btn>
                        </v-badge>
                    </v-row>
                </v-container>
            </div>
            <div class="box">
                <v-container>
                    <v-menu offset-y>
                        <template v-slot:activator="{on}">
                            <v-btn color="primary" dark v-on="on">dropdown</v-btn>
                        </template>
                        <v-list>
                            <v-list-item v-for="item in items" :key="item.title">
                                <v-list-item-title>{{ item.title }}</v-list-item-title>
                            </v-list-item>
                        </v-list>

                    </v-menu>
                </v-container>

            </div>
            <div class="box">
                <v-checkbox :label="`Checkbox 1: ${checkbox.toString()}`" v-model="checkbox">
                </v-checkbox>
            </div>
            <div class="box">
                <v-container fluid>
                    <v-combobox :items="things" label="combobox" outlined multiple dense></v-combobox>
                </v-container>
            </div>
            <div class="box">
                <v-file-input accept="image/*" label="File input"></v-file-input>
            </div>
            <div class="box">
                <v-container>
                    <v-row>
                        <v-col cols="9">
                            <v-otp-input :length="length" v-model="otp"></v-otp-input>
                        </v-col>
                        <v-col cols="2">
                            <v-btn :disabled="!isActive" class="my-3">Read</v-btn>
                        </v-col>
                    </v-row>
                </v-container>
            </div>
            <div class="box">
                <v-container>
                    <v-radio-group v-model="radios">
                        <v-radio value="Google">
                            <template v-slot:label>
                                Google
                            </template>
                        </v-radio>
                        <v-radio value="Duckduckgo">
                            <template v-slot:label>
                                Duckduckgo
                            </template>
                        </v-radio>
                    </v-radio-group>
                </v-container>
            </div>
            <div class="box">
                <v-container>
                    <v-sheet color="red " height="30" width="85">
                        <v-switch :label=" Switch.toString()" v-model="Switch"></v-switch>
                    </v-sheet>
                </v-container>
            </div>
            <div class="box">
                <v-container>
                    <v-textarea outlined label="Outlined textarea" value="The Woodman set to work at once, and so sharp was his axe that the tree was soon chopped nearly through."></v-textarea>
                </v-container>
            </div>
            <div class="box text-center">
                <v-pagination v-model="page" :length="4" circle></v-pagination>
            </div>
            <div class="box">
                <v-parallax height="200" src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"></v-parallax>
            </div>
            <div class="box">
                <v-menu ref="menu" transition="scale-transition" offset-y min-width="auto">
                    <template v-slot:activator="{on}">
                        <v-text-field v-model="date" prepend-icon="mdi-calendar" readonly v-on="on"></v-text-field>
                    </template>
                    <v-date-picker v-model="date"></v-date-picker>
                </v-menu>
            </div>

            <div class="box">
                <v-container>
                    <v-progress-linear height="20" value="10"></v-progress-linear>
                </v-container>
            </div>
            <div class="box">
                <v-container>
                    <v-rating v-model="rating"></v-rating>
                </v-container>
            </div>
           
        </div>

    </v-flex>
</div>
</template>

<script>
export default {
    name: 'flex',
    data() {
        return {
            items: [{
                    title: 'Click Me'
                },
                {
                    title: 'Click Me'
                },
                {
                    title: 'Click Me'
                },
                {
                    title: 'Click Me 2'
                },
            ],
            checkbox: true,
            select: ['Vuetify', 'Programming'],
            things: ['programming', 'designing', 'app', 'web'],
            otp: '',
            length: 7,
            radios: 'Google',
            Switch: true,
            page: 1,
            menu: false,
            menu2: false,
            date: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
            rating: 3,
        }
    },
    computed: {
        isActive() {
            return this.otp.length === this.length
        }
    }
}
</script>

<style lang="scss" scoped>
.box {
    width: 400px;
    height: 200px;
    background: red;
    margin-left: 10px;
    margin-top: 10px;
    margin-bottom: 10px;
    text-align: center;

}
</style>
