<template>
    <v-col cols="12">
        <v-card>
            <v-card-title>File</v-card-title>
            <v-divider></v-divider>
            <v-container>
                <v-row>
                    <v-col cols="12" sm="4">
                        <v-file-input prepend-icon="mdi-music" label="Music File" outlined></v-file-input>
                    </v-col>
                    <v-col cols="12" sm="4">
                        <v-file-input prepend-icon="mdi-music" label="Music Preview" outlined></v-file-input>
                    </v-col>
                    <v-col cols="12" sm="4">
                        <v-file-input prepend-icon="mdi-json" label="Global Storyboard"></v-file-input>
                    </v-col>
                </v-row>
            </v-container>
        </v-card>
    </v-col>
</template>

<script>
export default {
    name: "file-handler",
    data() {
        return {
            music: null,
            music_preview: null,
            storyboard: null
        };
    },
    methods: {
        setMusic(val) {
            console.log(val);
            this.music = val;
        },
        setMusicPreview(val) {
            console.log(val);
            this.music_preview = val;
        },
        setStoryboard(val) {
            console.log(val);
            this.storyboard = val;
        }
    }
};
</script>

<style>
</style>