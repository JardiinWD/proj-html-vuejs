<template>
        <!-- Speciality services goes here v - CO -->   
        <div :class="specialty_cont">
            <div :class="specialty_row">
                <!-- Descrizione delle specialità h-40 -->
                <div :class="specialty_desc">
                    <!-- titolo -->
                    <h2 class="pt-3 pb-4 title_specialty">{{specialty_title}}</h2>
                    <!-- Paragrafo -->                   
                    <p class="pt-3 w-75 para_specialty">{{specialty_p}}</p>
                </div>
                <!-- Card dei servizi -->
                <div :class="specialty_cards_cont">
                    <!-- Queste card sono dinamiche v-for --> 
                    <div v-for="(element, index) in cards_content" :class="specialty_single_card" :key="index">
                        <!-- Icona superiore e titolo --> 
                        <div class="col-9 h_30 flex_cent flex-column">
                            <!-- Logo (da font-awesome) -->
                            <div :class="scard_icon"><font-awesome-icon class="big_icons" :icon="element.icon" /></div>
                            <!-- Nome prodotto -->                            
                            <div :class="scard_title"><h5 class="pt-4">{{element.title}}</h5></div>
                        </div>
                        <!-- lorem ipsum --> 
                        <div :class="scard_text"><span>{{element.text}}</span></div>
                        <!-- Bottone learn more -->                    
                        <div class="h_10 w-100 flex_cent"><button :class="scard_button">{{element.about}}</button></div>
                    </div>
                </div>
            </div>           
        </div>  
</template>

<script>
export default {
    name:'SpecialityComponent',
    data() {
        return {
            /* Classi dinamiche - container e Row */
            specialty_cont : "container-fluid spec_services cont_cent",
            specialty_row: "row flex_cent h-100 w-100 p-0 flex-wrap",
            /* Classi dinamiche - Descrizione */
            specialty_desc: "col-6 h_40 flex_cent flex-column",
            /* Classi dinamiche - Cards */
            specialty_cards_cont:"col-8 gap-5 h_60 d-flex justify-content-center align-items-start p-0",
            specialty_single_card:"col-3 product_service_card h-75 flex_cent flex-column", 
            /* Classi dinamiche - Singola card */  
            scard_title: "col-12 h_40",
            scard_text: "h_60 col-10 pt-4 span_specialty_card",   
            scard_icon: "col-12 h_60 pt-4", 
            scard_button: "btn btn-primary w-100 btn_services",
            /* Contenuto Dinamico */
            specialty_title : "Specialty Services",
            specialty_p : "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos commodi totam autem, nesciunt deleniti dolorem eos reprehenderit consequatur excepturi ea?",


            
            /* Array di oggetto per dinamicità cards */
            cards_content: [
                /* Prima card - Small Business Loans */
                {
                icon: "fa-solid fa-globe",
                title: "Small Business Loans",
                text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quis velit doloremque tenetur quam deleniti sed at minus aperiam ipsa qui inventore consectetur",
                about:"Learn More"
                },
                /* Seconda Card - Credit Rating Advice */
                {
                icon: "fa-solid fa-gem",
                title: "Credit Rating Advice",
                text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quis velit doloremque tenetur quam deleniti sed at minus aperiam ipsa qui inventore consectetur",
                about:"Learn More"
                },
                /* Terza card - Fast Crowd Funding */
                {
                icon: "fa-solid fa-chart-line",
                title: "Fast Crowd Funding",
                text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quis velit doloremque tenetur quam deleniti sed at minus aperiam ipsa qui inventore consectetur",
                about:"Learn More"
                }        
            ]
        }
    },
}
</script>

<style lang="scss" scoped>
/* Import del foglio di stile */
@import '@/assets/sass/partials/main.scss';
</style>