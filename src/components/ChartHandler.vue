<template>
    <v-expansion-panels dark>
        <v-expansion-panel>
            <v-expansion-panel-header :class="color" class="accent-4">{{difficulty}}</v-expansion-panel-header>
            <v-expansion-panel-content class="pt-5 darken-4" :class="color">
                <v-text-field type="number" outlined prepend-icon="mdi-numeric" label="Difficulty"></v-text-field>
                <v-file-input label="Chart File" outlined prepend-icon="mdi-json"></v-file-input>
                <v-text-field label="Difficulty Name" prepend-icon="mdi-tag"></v-text-field>
                <v-file-input label="Music Override" prepend-icon="mdi-music"></v-file-input>
            </v-expansion-panel-content>
        </v-expansion-panel>
    </v-expansion-panels>
</template>

<script>
export default {
    name: "chart-handler",
    props: ["difficulty", "color"],
    data() {
        return {};
    }
};
</script>

<style>
</style>