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
                    <v-text-field
                      v-model="dataInicio"
                      label="Data início"
                      outlined
                      dense
                      placeholder="DD/MM/AAAA"
                      persistent-placeholder
                    />
                  </v-col>
                  <v-col cols="6">
                    <v-text-field
                      v-model="dataFinal"
                      label="Data final"
                      outlined
                      dense
                      placeholder="DD/MM/AAAA"
                      persistent-placeholder
                    />
                  </v-col>
                </v-row>
                <v-row>
                  <v-col cols="6">
                    <v-text-field
                      v-model="valor"
                      label="Valor"
                      outlined
                      dense
                      placeholder=""
                      persistent-placeholder
                    />
                  </v-col>
                  <v-col cols="6">
                    <v-text-field
                      v-model="valorAtual"
                      label="Valor atualizado"
                      outlined
                      dense
                      placeholder=""
                      persistent-placeholder
                    />
                  </v-col>
                </v-row>
            </v-card-text>
            <v-row>
              <v-col class="botao">
                <v-btn color="primary" dark style="margin-right: 5px">Calcular</v-btn>
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
  export default {
    data(){
      return{
        dataInicio: '',
        dataFinal: '',
        valor: '',
        valorAtual: '',
      }
    }
  }
</script>

<style scoped>
#login-page {
  background-color: #b6d2ed;
}

.botao{
  text-align: center !important;
}
</style>
