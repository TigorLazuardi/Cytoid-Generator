<template>
    <v-row>
        <v-col cols="12" md="6">
            <v-text-field
                label="Charter"
                v-model="payload.charter"
                outlined
                prepend-inner-icon="mdi-text"
            ></v-text-field>
        </v-col>
        <v-col cols="12" md="6">
            <v-text-field
                label="Chart ID"
                v-model="payload.id"
                :placeholder="data._id"
                prepend-inner-icon="mdi-text"
                messages="Auto generate if left empty"
                outlined
            ></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {
    name: "charter-metadata",
    props: ["data"],
    data() {
        return {
            payload: {
                charter: "",
                id: ""
            }
        };
    },
    watch: {
        payload(val) {
            let { charter, id } = val;
            if (charter && !id) {
                val.id = data._id;
            }
            this.$emit("set-chart", val);
        }
    }
};
</script>

<style>
</style>