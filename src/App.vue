<template>
    <v-app>
        <v-app-bar app>
            <v-toolbar-title class="headline text-uppercase">
                <span>Cytoid level Generator</span>
            </v-toolbar-title>
        </v-app-bar>

        <v-content>
            <keep-alive>
                <router-view :preview="preview" />
            </keep-alive>
        </v-content>
    </v-app>
</template>

<script>
export default {
    name: "App",
    components: {},
    data: () => ({
        preview: {}
    }),
    methods: {
        setPreview(val) {
            this.preview = val;
        }
    }
};
</script>
