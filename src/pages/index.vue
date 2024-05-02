<template>
<v-app :style="{background:$vuetify.theme.themes.dark.colors.primary}">
    <v-main>
        <Navbar/>
        <v-container fluid>
           <v-row>
            <v-col cols="12" sm="2">
                <v-row>
                    <v-col cols="12" sm="12">
                        <v-expansion-panels v-model="panel">
                            <v-expansion-panel class="co"  bg-color="#1f1f1f">
                                <v-expansion-panel-title  color="text-white bg-orange">
                                <v-icon icon="mdi mdi-menu" class="ml-n4 mr-1"></v-icon> Category
                            </v-expansion-panel-title>
                            <v-expansion-panel-text>
                                <v-list class="cat" density="compact" bg-color="#1f1f1f">
                                    <v-list-item v-for="(item,i) in items" :key="i" :value="item" color="orange" variant="plain" class="ml-n2">
                                        <v-list-item-title class="text-caption">{{ item.text }}</v-list-item-title>
                                    </v-list-item>
                                </v-list>
                            </v-expansion-panel-text>
                            </v-expansion-panel>
                        </v-expansion-panels>
                    </v-col>
                    <v-col col="12" sm="12">
                        <v-card class="co" bg-color="#1f1f1f">
                            <v-list lines="two" class="cat pro"  bg-color="#1f1f1f">
                                <v-list-subheader inset class="ml-n10 text-white">Hot Products</v-list-subheader>
                                <v-list-item v-for="product in products" :key="product.title" :title="product.title" color="red">
                                    <template v-slot:subtitle>
                                        <v-list-item-subtitle class="text-caption text-orange">{{ product.subtitle }}</v-list-item-subtitle>
                                    </template>
                                    <template v-slot:prepend>
                                        <v-avatar variant="outlined" rounded="0" color="grey">
                                        <v-img color="white" :src="product.image"></v-img>
                                    </v-avatar>
                                    </template>
                                </v-list-item>
                            </v-list>
                        </v-card>
                    </v-col>
                    <v-col cols="12" sm="12">
                        <v-card class="co pa-2">
                            <h5 class="ml-4 text-white"> Tag Cloud</h5>
                            <v-chip class="ma-2 tag" label color="white">
                                Desserts
                            </v-chip>
                            <v-chip class="ma-2 tag" label color="white">
                                Passta
                            </v-chip>
                            <v-chip class="ma-2 tag" label color="white">
                                Drinks
                            </v-chip>
                            <v-chip class="ma-2 tag" label color="white">
                                Desserts
                            </v-chip>
                        </v-card>
                       
                    </v-col>
           
                </v-row>
            </v-col>
            <v-col cols="12" sm="8">
                <v-row>
                            <v-col cols="12" sm="12">
                                <v-carousel :show-arrows="false">
                                <v-carousel-item v-for="(item,i) in pictures" :key="i" :src="item.src" cover></v-carousel-item>
                                </v-carousel>
                            </v-col>
                            <v-col cols="12" sm="12">
                                <v-toolbar color="#1F1F1F"> 
                                    <v-toolbar-title>Safe and on time home deliveries</v-toolbar-title>
                                <v-spacer></v-spacer>
                                <v-btn color="white" class="btn"> View Offers</v-btn>
                                </v-toolbar>
                            </v-col>
                            <v-col cols="12" sm="12">
                                <v-card class="tb" flat  >
                                    <v-tabs v-model="tab" color="grey" align-tabs="end">
                                    <v-tab :value="1">Desserts</v-tab>
                                    <v-tab :value="2">Drinks</v-tab>
                                    <v-tab :value="3">Pasta</v-tab>
                                    </v-tabs>
                                    <v-window v-model="tab" class="co">
                                    <v-window-item v-for="n in 3" :key="n" :value="n">
                                    <v-container fluid >
                                        <v-row>
                                            <v-col v-for="(dish,i) in dishes" :key="i" cols="12" md="3">
                                            <v-hover v-slot="{isHovering,props}" open-delays="200">
                                            <v-card color="#111111" v-bind="props">
                                            <v-img height="90" :src="dish.image" class="mt-6">
                                            <v-card-item class="text-center mt-14">
                                                <v-card-subtitle>
                                                    <span>{{ dish.title }}</span>
                                                </v-card-subtitle>
                                                <v-card-title class="text-caption text-orange">
                                                    {{ dish.money }}
                                                </v-card-title>
                                            </v-card-item>
                                            <v-expand-transition>
                                                <div v-if="isHovering" class="d-flex transition-fast-in-fast-out bg-grey-darken-3 v-card--reveal text-h2" style="height: 100%;">
                                                <v-btn density="compact" icon="mdi mdi-magnify" class="mr-2"></v-btn>
                                                <v-btn density="compact" icon="mdi mdi-heart-outline" class="mr-2"></v-btn>
                                                <v-btn density="compact" icon="mdi mdi-sync" class="mr-2"></v-btn>
                                                </div>
                                            
                                            </v-expand-transition>
                                            </v-img>
                                            </v-card>
                                            </v-hover>
                                            </v-col>
                                            <v-toolbar color="transparent">
                                                <v-toolbar-title class="text-white">Product List</v-toolbar-title>
                                                <v-spacer></v-spacer>
                                                <v-icon icon="mdi mdi-chevron-left-circle"></v-icon>
                                                <v-icon icon="mdi mdi-chevron-right-circle"></v-icon>
                                            </v-toolbar>
                                            <v-col cols="12" sm="12">
                                                <v-sheet class="mx-auto co" elevation="8" max-width="800" color="#1f1f1f">
                                                    <v-slide-group v-model="model" class="pa-4" center-active show-arrows >
                                                    <v-slide-group-item  v-for="(dish,i) in dishes" :key="i" v-slot="{isSelected,toggle}">
                                                        <v-card rounded="lg" :color="isSelected ? 'primary':'#111111'" class="ma-4 btn" height="100" width="200" @click="toggle">
                                                        <v-row>
                                                            <v-col cols="12" sm="6">
                                                                <v-img height="100" :src="dish.image" class="ml-5"></v-img>
                                                            </v-col>
                                                            <v-col cols="12" sm="6" class="text-center mt-6">
                                                                <span>{{ dish.title }}</span>
                                                                <h5 class="text-caption text-orange">
                                                                    {{ dish.money }}
                                                                </h5>
                                                            </v-col>
                                                        </v-row>
                                                        <div class="f-flex fill-height align-center justify-center">
                                                            <v-scale-transition>
                                                                <v-icon v-if="isSelected" color="white" size="48" icon="mdi-close-circle-outline"></v-icon>
                                                            </v-scale-transition>
                                                        </div>
                                                        </v-card>  
                                                    </v-slide-group-item>
                                                    </v-slide-group>
                                                </v-sheet>
                                            </v-col>
                                        </v-row>
                                    </v-container>
                                    </v-window-item>
                                    </v-window>
                                </v-card>
                            </v-col>
                           
                </v-row>
            </v-col>
            <v-col cols="12" sm="2" >
                        <v-card class="co">
                            <v-list lines="two" class="cat pro" bg-color="#1f1f1f">
                                <v-list-item v-for="offer in offers" :key="offer.title" :title="offer.title" color="red">
                                <template v-slot:subtitle>
                                    <v-list-item-subtitle  class="text-caption">{{ offer.subtitle }}</v-list-item-subtitle>
                                </template>
                                <template v-slot:prepend>
                                    <v-icon :icon="offer.icon" large color="orange"></v-icon>
                                </template>
                                </v-list-item>
                            </v-list>
                        </v-card>
                        <v-col sm="12" cols="12">
                        <v-card class="co pa-2">
                            <div class="float-sm-left">
                                <span class="ml-4 text-white">Tag Cloud</span>
                                <v-icon icon="mdi mdi-chevron-right-circle" class="ml-10"></v-icon>
                                <v-icon icon="mdi mdi-chevron-left-circle"></v-icon>
                            
                            </div>
                            <div class="text-center">
                                <v-avator variant="outlined" color="white" class="mt-2">
                                <v-img src="" alt="John"></v-img>    
                                </v-avator>
                                <h5 class="text-grey mt-3">Sabina</h5>
                                <p class="text-grey mt-2 text-caption">
                                    LOREMMS MSM MS MSMMM SMS MQMMSSMDSM
                                </p>
                            </div>
                        </v-card>
                       </v-col>
                        <v-col sm="12" cols="12">
                            <v-card class="co pa-2">
                            <div class="float-sm-left mb-4">
                                <span class="ml-4 text-white">Latest News</span>
                                <v-icon icon="mdi mdi-chevron-right-circle" class="ml-6"></v-icon>
                                <v-icon icon="mdi mdi-chevron-left-circle"></v-icon>
                           

                            </div>
                            <div class="text-center">
                                <v-img src="" alt="pi" width="200"></v-img>
                            </div>
                            <h5 class="text-grey mt-3">purous emsm sdsdsmd</h5>
                            <p class="text-grey mt-2 text-caption">July 30, 2024</p>

                        </v-card>
                        </v-col>
                       
                    </v-col>
       
             

           </v-row>

        </v-container>
    </v-main>
</v-app>
</template>

<script>
import Navbar from '@/components/Navbar.vue';
import footer from '@/components/AppFooter.vue';
export default {
    components:[
        Navbar,
        footer
    ],
    data:() =>({
        panel:[0],
        disabled:false,
        tab:null,
        model:null,
        items:[
            {text:"Desserts"},
            {text:"Drinks"},
            {text:"Pasta"},
            {text:"Pizza"},
        ],
        products:[
            {
                title:'pizza',
                subtitle:"$800.00",
                image:"side-1.jpg",
            },
            {
                title:'cheese',
                subtitle:"$800.00",
                image:"side-1.jpg",
            },
            {
                title:'Drinks',
                subtitle:"$800.00",
                image:"side-1.jpg",
            },
            {
                title:'pizza',
                subtitle:"$800.00",
                image:"side-1.jpg",
            },
        ],
        offers:[
            {
            title:'Free Shipping',
            subtitle:"grab now",
            icon:"mdi mdi-airplane"
        },
        {
            title:'Free Shipping',
            subtitle:"grab now",
            icon:"mdi mdi-basket"
        },
    ],
    pictures:[
        {
            src:"side-1.jpg",
        },
        {
            src:"side-1.png",
        },
        {
            src:"side-2.jpg",
        },
        {
            src:"side-2.png",
        },
    ],
    dishes:[
        {image:"side-2.png",title:"Plat unique",money:"$10.0"},
        {image:"side-2.png",title:"Plat unique",money:"$10.0"},
        {image:"side-2.png",title:"Plat unique",money:"$10.0"},
        {image:"side-2.png",title:"Plat unique",money:"$10.0"},


    ]


    })
}
</script>
<style>
.bg-black {
  background-color: black;
}

.co{
    background-color: #1f1f1f;
}
.tb{
    background-color: #2f2f2f;
}
.cat{
    background-color: #1f1f1f;
    color: white;
}
.tag:hover{
    color:orange;
}
.btn{
    background-color: #111111;
}
.v-card--reveal{
    align-items: center;
    bottom: 0;
    justify-content: center;
    opacity: 0.9;
    position: absolute;
    width: 100%;
}
</style>