<template>
    <v-row>
        <v-col cols="12" md="6">
            <v-text-field
                label="Schema Version"
                disabled
                value="2"
                messages="Unless otherwise stated, Schema Version is always '2'"
            ></v-text-field>
        </v-col>
        <v-col cols="12" md="6">
            <v-text-field label="Chart Version" type="number" placeholder="1" outlined></v-text-field>
        </v-col>
    </v-row>
</template>

<script>
export default {};
</script>

<style>
</style>