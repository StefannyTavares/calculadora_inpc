<template>
    <div>
        <v-menu
            ref="menu1"
            v-model="menu1"
            :close-on-content-click="false"
            transition="scale-transition"
            offset-y
            max-width="290px"
            min-width="auto"
        >
            <template v-slot:activator="{ on, attrs }">
                <v-text-field
                    v-model="dateFormatted"
                    :label='label' 
                    hint="MM/YYYY"
                    persistent-hint
                    :outlined="outlined"
                    :dense="dense"
                    :placeholder="placeholder"
                    prepend-icon="mdi-calendar"
                    v-bind="attrs"
                    @blur="date = parseDate(dateFormatted)"
                    v-on="on"
                    locale="pt-BR"
                ></v-text-field>
            </template>
            <v-date-picker
                v-model="date"
                no-title
                @input="menu1 = false"
                type="month"
            ></v-date-picker>
        </v-menu>
    </div>
</template>

<script>
export default {
    props: {
        outlined: Boolean,
        dense: Boolean,
        label: {
          type: String,
        },
        placeholder: {
            type: String,
        },
    },

    data: vm => ({
      date: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
      dateFormatted: vm.formatDate((new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10)),
      menu1: false,
    }),

    computed: {
      computedDateFormatted () {
        return this.formatDate(this.date)
      },
    },

    watch: {
      date (dataNova) {
        this.dateFormatted = this.formatDate(dataNova)
      },
    
      dateFormatted () {
        this.$emit('input', this.dateFormatted);
      },
    },

    methods: {
      formatDate (date) {
        if (!date) return null

        const [year, month] = date.split('-')
        return `${month}/${year}`
      },
      parseDate (date) {
        if (!date) return null

        const [month, year] = date.split('/')
        return `${year}-${month.padStart(2, '0')}`
      },
    },
};
</script>

<style scoped>
</style>