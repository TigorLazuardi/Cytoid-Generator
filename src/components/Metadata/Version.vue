<template>
    <v-row>
        <v-col cols="12" md="6">
            <v-text-field
                label="Chart Version"
                type="number"
                v-model="_version"
                placeholder="1"
                outlined
                prepend-inner-icon="mdi-numeric"
            ></v-text-field>
        </v-col>
        <v-col cols="12" md="6">
            <v-text-field
                label="Schema Version"
                disabled
                value="2"
                messages="Unless otherwise stated, Schema Version is always '2'"
            ></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {
    name: "version-metadata",
    props: ["version"],
    computed: {
        _version: {
            get() {
                return this.version;
            },
            set(val) {
                this.$emit("set-version", val);
            }
        }
    }
};
</script>

<style>
</style>