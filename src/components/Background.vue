<template>
    <!-- Previous/ Next buttons are only to be shown, when in Gallery mode -->
    <!-- Cycling stops when chosing Gallery Mode -->
    
    <v-carousel :show-arrows="showingArrows" hide-delimiters style="position:fixed; top: 0px;" height="100%">
        <v-carousel-item 
            v-for="foto in fotos_arr" :key="foto.id"
            reverse-transition="fade-transition"
            transition="fade-transition"
        >
            <v-img :src="foto.src" min-height="100%"/>
            <h1 style="position: fixed; bottom:0px; left:0px" v-show="showDescription" class="text-h3 ma-5 white--text">{{foto.title}}</h1>
        </v-carousel-item>
    </v-carousel>
</template>

<script>
export default {
    data(){
        return{
            fotos_arr: [
                {
                    id:1,
                    src: require('../assets/foto1.jpg'),
                    title: 'A beautiful mountain, Spain 2002',
                },
                {   
                    id:2,
                    src: require('../assets/foto2.jpg'),
                    title: 'A beautiful landscape, Germany 2010',
                },
                {
                    id:3,
                    src: require('../assets/foto3.jpg'),
                    title: 'A beautiful nature, Amazonas 1995',
                }
            ],
            cycling: false,
            showingArrows: false,
            showDescription: false
        }
    },
    mounted(){
        this.$UIEvents.on("galleryWasOpened", () =>{
            this.cycling = false;
            this.showingArrows = true;
            this.showDescription = true;    
        });
        this.$UIEvents.on("galleryWasClosed", () =>{
            this.cycling = false;
            this.showingArrows = false;
            this.showDescription = false;
        });
    }
}
</script>
<style scoped>
.background-mode{
    
}
.gallery-mode{

}
</style>