<template>
    <v-container>
        <v-row>
            <FileHandler @FileHandling="FileHandling" />
            <v-col cols="12">
                <v-toolbar dark class="py-10 py-sm-5" style="height: 135px">
                    <div class="d-flex flex-column justify-center">
                        <v-toolbar-title>Chart</v-toolbar-title>
                        <v-toolbar-items>*Please select at least one difficulty</v-toolbar-items>
                        <v-toolbar-items>**Expanding the panel means you plan to use the difficulty. If not using them, please close the panel, or it will be subjected to validation check</v-toolbar-items>
                    </div>
                </v-toolbar>
            </v-col>
            <v-col cols="12" md="4">
                <ChartHandler :difficulty="'Easy'" :color="'cyan'" />
            </v-col>
            <v-col cols="12" md="4">
                <ChartHandler :difficulty="'Hard'" :color="'deep-purple'" />
            </v-col>
            <v-col cols="12" md="4">
                <ChartHandler :difficulty="'EX'" :color="'red'" />
            </v-col>
            <v-col cols="12">
                <v-toolbar dark>
                    <v-toolbar-title>Metadata</v-toolbar-title>
                </v-toolbar>
            </v-col>
            <v-col cols="12">
                <v-card>
                    <v-container>
                        <Version :version="version" @set-version="setVersion" />
                        <Title @set-title="setTitle" />
                        <Artist @set-artist="setArtist" />
                    </v-container>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import ChartHandler from "../components/ChartHandler";
import FileHandler from "../components/FileHandler";
import Version from "../components/Metadata/Version";
import Title from "../components/Metadata/Title";
import Artist from "../components/Metadata/Artist";

export default {
    name: "home",
    data() {
        return {
            file: {
                background: null,
                music: null,
                music_preview: null
            },
            music: {
                path: ""
            },
            music_preview: {
                path: ""
            },
            background: {
                path: ""
            },
            version: 1,
            title: "",
            title_localized: undefined,
            artist: "",
            artist_localized: undefined
        };
    },
    components: {
        FileHandler,
        ChartHandler,
        Version,
        Title,
        Artist
    },
    methods: {
        FileHandling(payload) {
            this.file.music = payload.music;
            this.file.music_preview = payload.music_preview;
            this.file.background = payload.background;
            if (payload.background) {
                this.background.path = payload.background.path.split("/").pop();
            }
            if (payload.music) {
                this.music.path = payload.music.path.split("/").pop();
            }
            if (payload.background) {
                this.music_preview.path = payload.music_preview.path
                    .split("/")
                    .pop();
            }
        },
        setVersion(val) {
            this.version = val;
        },
        setTitle({ title, title_localized }) {
            if (title) {
                this.title = title;
            }
            if (title_localized) {
                this.title_localized = title_localized;
            }
        },
        setArtist({ artist, artist_localized }) {
            if (artist) {
                this.artist = artist;
            }
            if (artist_localized) {
                this.artist_localized = artist_localized;
            }
        }
    }
};
</script>
