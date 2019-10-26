<template>
    <v-col cols="12">
        <v-card>
            <v-toolbar flat dark color="indigo">
                <v-toolbar-title>Required Files</v-toolbar-title>
            </v-toolbar>
            <v-divider></v-divider>
            <v-container>
                <v-row>
                    <v-col cols="12" md="4">
                        <v-file-input
                            @change="setMusic"
                            prepend-icon="mdi-music"
                            label="Music File"
                            accept=".mp3"
                            outlined
                        ></v-file-input>
                    </v-col>
                    <v-col cols="12" md="4">
                        <v-file-input
                            @change="setMusicPreview"
                            prepend-icon="mdi-music"
                            label="Music Preview"
                            accept=".mp3"
                            outlined
                        ></v-file-input>
                    </v-col>
                    <v-col cols="12" md="4">
                        <v-file-input
                            @change="setBackground"
                            prepend-icon="mdi-image"
                            label="Background Image"
                            accept="image/jpeg, image/png"
                            outlined
                        ></v-file-input>
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
            payload: {
                music: null,
                music_preview: null,
                background: null
            }
        };
    },
    methods: {
        setMusic(val) {
            console.log(val);
            this.payload.music = val;
            this.$emit("FileHandling", this.payload);
        },
        setMusicPreview(val) {
            this.payload.music_preview = val;
            this.$emit("FileHandling", this.payload);
        },
        setBackground(val) {
            this.payload.background = val;
            this.$emit("FileHandling", this.payload);
        }
    }
};
</script>

<style>
</style>