<template>
    <v-app>
        <v-container fluid fill-height id="login-page">
            <v-layout align-center justify-center>
                <v-flex :style="{ 'max-width': '600px' }">
                    <v-toolbar color="primary" dark>
                        <v-toolbar-title>Calculadora INPC</v-toolbar-title>
                    </v-toolbar>
                    <v-card elevation="12">
                        <v-card-text>
                            <v-row>
                                <v-col cols="6">
                                    <date-picker
                                        v-model="dataInicio"
                                        label="dataInicio"
                                        outlined
                                        dense
                                        placeholder=""
                                    />
                                </v-col>
                                <v-col cols="6">
                                    <date-picker
                                        v-model="dataFinal"
                                        label="dataFinal"
                                        outlined
                                        dense
                                        placeholder=""
                                    />
                                </v-col>
                            </v-row>
                            <v-row>
                                <v-col cols="6">
                                    <input-money
                                        v-model="valor"
                                        label="Valor"
                                        outlined
                                        dense
                                        placeholder=""
                                        options
                                    />
                                </v-col>
                                <v-col cols="6">
                                    <input-money
                                        v-model="valorAtual"
                                        label="Valor atualizado"
                                        outlined
                                        dense
                                        placeholder=""
                                    />
                                </v-col>
                            </v-row>
                        </v-card-text>
                        <v-row>
                            <v-col class="botao">
                                <v-btn
                                    color="primary"
                                    dark
                                    style="margin-right: 5px"
                                    >Calcular</v-btn
                                >
                                <v-btn color="red" dark>Limpar</v-btn>
                            </v-col>
                        </v-row>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>
    </v-app>
</template>

<script>
import datePicker from '../shared/datePicker.vue';
import inputMoney from '../shared/inputMoney.vue'

export default {
    components: {
        datePicker, inputMoney
    },
    data() {
        return {
            dataInicio: "",
            dataFinal: "",
            valor: "",
            valorAtual: "",
        };
    },
};
</script>

<style scoped>
#login-page {
    background-color: #b6d2ed;
}

.botao {
    text-align: center !important;
}
</style>
