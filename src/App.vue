<template>
<v-app>
    <v-app-bar flat app>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-toolbar-title>Collapsing Bar</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn class="right">
            <router-link to="/">Home</router-link>
        </v-btn>
        <v-btn>
            <router-link to="/about">About</router-link>
        </v-btn>
        <v-btn>
            <router-link to="/form">Form</router-link>
        </v-btn>
        <v-btn>
            <router-link to="/flex">Flex</router-link>
        </v-btn>
    </v-app-bar>
    <v-main>
        <router-view />
    </v-main>
</v-app>
</template>

<script>
export default {
    name: 'App',

    data: () => ({
        //
    }),
};
</script>
