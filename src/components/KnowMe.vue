<template>
    <v-overlay z-index="0">
        <v-expand-transition>
            <v-card class="pa-5" color="yellow lighten-4" v-show="show">
                <v-card class="d-flex pa-2" elevation="10">
                    <v-img
                        src="../assets/picture.jpg"
                        width="20em"
                        v-show="showProfilePicture"/>
                    <v-container fill-height fluid>
                        <v-row align="center" justify="center">
                            <v-col align="center" justify="center">
                                    <v-card max-width="25em" class="ma-2 pa-5" tile elevation="10">
                                    <h1>Acerca de mí</h1>
                                    <br/>
                                    <p>¡Hola ahí! Soy Geraldo, un fotografo profesional madrileño con 15 años de experiencia. Desde pequeño estuve muy interesado en la fotografía.</p>
                                    <p>La fotografía es mí pasión. Para mí es un arte que no tiene igual. Espacios, colores, formas... la belleza esta por todos lados, esperando ser capturada.</p>
                                    </v-card>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </v-card>
        </v-expand-transition>
    </v-overlay>
</template>

<script>
export default {
    data(){
        return{
            show: false
        }
    },
    mounted(){
        this.show=true
    },
    computed:{
        showProfilePicture(){
            if(this.$vuetify.breakpoint.name=="xs"){
                return false
            }else{
                return true
            }
        }
    }
}
</script>