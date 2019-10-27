<template>
    <v-row>
        <v-col cols="12" md="6">
            <v-text-field
                label="Title"
                prepend-inner-icon="mdi-text"
                outlined
                v-model="payload.title"
            ></v-text-field>
        </v-col>
        <v-col cols="12" md="6">
            <v-text-field
                label="Title (Localized)"
                prepend-inner-icon="mdi-text"
                v-model="payload.title_localized"
            ></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {
    name: "title-metadata",
    data() {
        return {
            payload: {
                title: "",
                title_localized: ""
            }
        };
    },
    watch: {
        title(val) {
            this.$emit("set-title", this.payload);
        },
        title_localized(val) {
            this.$emit("set-title", this.payload);
        }
    }
};
</script>

<style>
</style>