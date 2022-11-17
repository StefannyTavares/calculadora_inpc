<template>
    <v-app>
        <v-container fill-height fluid id="principal">
            <v-layout align-center justify-center>
                <v-flex :style="{ 'max-width': '600px', 'padding': '-20px' }">
                    <v-toolbar color="primary" dark>
                        <v-toolbar-title>Calculadora INPC</v-toolbar-title>
                    </v-toolbar>
                    <v-card elevation="12">
                        <v-card-text>
                            <v-row>
                                <v-col cols="5" offset="1">
                                    <date-picker
                                        v-model="dataInicio"
                                        label="dataInicio"
                                        outlined
                                        dense
                                        placeholder=""
                                    />
                                </v-col>
                                <v-col cols="5">
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
                                <v-col cols="5" offset="1">
                                    <input-money
                                        v-model="valor"
                                        label="Valor"
                                        outlined
                                        dense
                                        placeholder=""
                                        options
                                    />
                                </v-col>
                                <v-col cols="5">
                                    <input-money
                                        v-model="valorAtual"
                                        label="Valor atualizado"
                                        outlined
                                        dense
                                        placeholder=""
                                        disabled
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
import inputMoney from '../shared/inputMoney.vue';

export default {
    components: {
        datePicker, inputMoney
    },
    data() {
        return {
            dataInicio: '',
            dataFinal: '',
            valor: '',
            valorAtual: '',
        };
    },
};
</script>

<style scoped>
#principal {
    background-image: url(https://images.pexels.com/photos/259209/pexels-photo-259209.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1);
    background-size: cover;
    padding: 100px;
    width: 2000px;
}

.botao {
    text-align: center !important;
}
</style>
