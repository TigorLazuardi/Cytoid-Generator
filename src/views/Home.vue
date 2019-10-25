<template>
    <v-container>
        <v-row>
            <FileHandler @FileHandling="FileHandling" />
        </v-row>
    </v-container>
</template>

<script>
import FileHandler from "../components/FileHandler";

export default {
    name: "home",
    data() {
        return {
            file: {
                image: null,
                music: null,
                music_preview: null
            },
            music: null,
            music_preview: null
        };
    },
    components: {
        FileHandler
    },
    methods: {
        FileHandling(payload) {}
    }
};
</script>
