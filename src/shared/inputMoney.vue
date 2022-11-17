<template>
    <div>
        <vuetify-money
            v-model="model"
            :label="label"
            :placeholder="placeholder"
            :outlined="outlined"
            :options="options"
            :dense="dense"
            persistent-placeholder
        />
    </div>
</template>

<script>
export default {
    name: 'InputMoney',
    props: {
        label: {
            type: String,
        },
        placeholder: {
            type: String,
        },
        outlined: Boolean,
        clearable: Boolean,
        dense: Boolean,
        persistentPlaceholder: Boolean,
    },
    data() {
        return{
            model: '',
            options: {
                locale: "pt-BR",
                prefix: "R$",
                suffix: "",
                length: 11,
                precision: 2,
            },
        }
    },

    watch: {
        model (novoValor) {
            this.$emit('input', novoValor);
        },
    }
};
</script>

<style scoped>
</style>