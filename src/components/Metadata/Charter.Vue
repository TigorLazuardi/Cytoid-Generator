<template>
    <v-row>
        <v-col cols="12" md="6">
            <v-text-field label="Charter" outlined prepend-inner-icon="mdi-text"></v-text-field>
        </v-col>
        <v-col cols="12" md="6">
            <v-text-field label="Chart ID" prepend-inner-icon="mdi-text" outlined></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {
    name: "charter-metadata",
    data() {
        return {};
    }
};
</script>

<style>
</style>