<template>
    <v-row>
        <v-col cols="12" md="6">
            <v-text-field label="Artist" outlined prepend-inner-icon="mdi-account"></v-text-field>
        </v-col>
        <v-col cols="12" md="6">
            <v-text-field label="Artist (Localized)" prepend-inner-icon="mdi-account"></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {
    name: "artist-metadata",
    data() {
        return {};
    }
};
</script>

<style>
</style>