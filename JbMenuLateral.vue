<template>
    <v-navigation-drawer fixed :clipped="$vuetify.breakpoint.mdAndUp" app v-model="abrir_menu" >
        <v-list>
            <v-list-tile v-for="item in itensMenu" :key="item.titulo" :href="item.href">
                <v-list-tile-action>
                    <div v-if="item.icone">
                        <v-icon v-if="item.icone" small>{{item.icone}}</v-icon>
                    </div>
                </v-list-tile-action>
                <v-list-tile-content>{{ item.titulo }}</v-list-tile-content>
            </v-list-tile>
        </v-list>
    </v-navigation-drawer>
</template>

<script>

export default {
    props:{
        value:Boolean, 
        itens:Array,
    },
    data: function () {
        return {
            abrir_menu: this.value,

            /** Modelo
                itens: [{ titulo: 'Dashboard', icone: 'fas fa-home', href: '/home' }]
             */
            itensMenu: this.itens,
        }
    },
    computed:{
    },
    methods: {
    },
    watch: {
        value(valor) {
            this.abrir_menu = valor
        }
    },
    mounted(){
    }

}

</script>


