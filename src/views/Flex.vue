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
            <div class="box"></div>
            <div class="box"></div>
            <div class="box"></div>
            <div class="box"></div>
            <div class="box"></div>
            <div class="box"></div>
            <div class="box"></div>
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
        }
    },
}
</script>

<style lang="scss" scoped>
.box {
    width: 400px;
    height: 200px;
    background: red;
    margin-left: 10px;
    margin-top: 10px;
    text-align: center;

}
</style>
