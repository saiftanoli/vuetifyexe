<template>
<v-app>

    <v-app-bar  app>
        <v-app-bar-nav-icon @click="drawer =!drawer">
        </v-app-bar-nav-icon>
        <v-toolbar-title>Navigation Drawer</v-toolbar-title>
        <v-spacer></v-spacer>
        <div class="hidden-sm-and-down">
            <router-link class="bb" to="/">
                <v-btn>Home</v-btn>
            </router-link>
            <router-link class="bb" to="/about">
                <v-btn>About</v-btn>
            </router-link>
            <router-link class="bb" to="/form">
                <v-btn>Form</v-btn>
            </router-link>
            <router-link class="bb" to="/flex">
                <v-btn>Flex</v-btn>
            </router-link>
        </div>
        <div class="hidden-md-and-up">
            <v-menu offset-y>
                <template v-slot:activator="{ on }">
                        <v-app-bar-nav-icon v-on="on">
                        </v-app-bar-nav-icon>
                </template>
                <v-list>
                    <v-list-item>
                        <v-list-item-title> <br>
                            <router-link class=" bb" to="/">
                                Home
                            </router-link> <br> <br>
                            <router-link class="bb" to="/about">
                                About
                            </router-link> <br> <br>
                            <router-link class="bb" to="/form">
                                Form
                            </router-link> <br> <br>
                            <router-link class="bb" to="/flex">
                                Flex
                            </router-link>
                        </v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>
        </div>
    </v-app-bar>
    <v-navigation-drawer app v-model="drawer">
        <v-list>
            <v-list-item>
                <v-list-item-content>
                    <v-list-item-title>
                        Saifullah
                    </v-list-item-title>
                    <v-list-item-subtitle>
                        @user
                    </v-list-item-subtitle>
                </v-list-item-content>
            </v-list-item>
            <v-divider></v-divider>
            <v-list-item v-for="item in items" :key="item.title">
                <v-list-item-icon>
                    <v-icon>{{item.icon}}</v-icon>
                </v-list-item-icon>
                <v-list-item-content>
                    <v-list-item-title>{{item.title}}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
    <v-main>
        <router-view />
    </v-main>
</v-app>
</template>

<script>
export default {
    name: 'App',
    data() {
        return {
            drawer: false,
            items: [{
                    title: 'Dashboard',
                    icon: 'mdi-view-dashboard'
                },
                {
                    title: 'Photos',
                    icon: 'mdi-image'
                },
                {
                    title: 'About',
                    icon: 'mdi-help-box'
                },
            ],

        }
    },
};
</script>

<style scoped>
.bb {
    text-decoration: none;
    margin-right: 8px;
}
</style>
