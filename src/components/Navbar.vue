<template>
<v-system-bar color="#1F1F1F">
    <span>Welcome to online Store</span>
    <v-spacer></v-spacer>
    <v-icon icon="mdi mdi-linkedin" class="ms-2"></v-icon>
</v-system-bar>
<v-app-bar height="100" flat color="#1F1F1F" >
    <v-app-bar-title><h2>SHOP</h2></v-app-bar-title>
    <v-spacer></v-spacer>
    <v-card color="#141415" flat outlined height="50" width="500" class="mt-6 pt-1">
        <v-row>
            <v-col cols="12" sm="10" >
                <v-text-field density="compact" placeholder="Search"></v-text-field>
            </v-col>
            <v-col cols="12" sm="2">
                <v-icon color="orange" icon="mdi mdi-magnify" size="large" class="mt-2 ml-4"></v-icon>
            </v-col>
        </v-row>
    </v-card>
    <v-spacer></v-spacer>
    <div>
        <span class="ml-4 text-caption">My Favorite</span><br/>
        <v-btn append-icon="mdi mdi-heart-outline" class="account"> Wishlist<template v-slot:append><v-icon></v-icon></template></v-btn>
    </div>
    <v-divider vertical inset class="mr-6"></v-divider>
    <div>
        <span class="ml-4 text-caption"> Login/Signup</span><br/>
        <v-btn append-icon="mdi mdi-lock-open-outline" class="account">My account
            <template v-slot:append>
                <v-icon></v-icon>
            </template>
        </v-btn>
    </div>
    <v-divider vertical inset class="mr-6"></v-divider>
    <v-icon class="mr-10"> mdi mdi-shopping-outline</v-icon>
</v-app-bar>
<v-app-bar height="50" flat color="#191919">
    <v-btn variant="text" color="orange">Home</v-btn>

    <v-btn variant="text" class="orange">Shop</v-btn>

    <v-btn variant="text" class="orange">Drinks</v-btn>

    <v-btn variant="text" class="orange">Blog</v-btn>

    <v-btn variant="text" class="orange">Contact US</v-btn>
    <v-btn variant="text" class="orange">Update To Pro</v-btn>
    <v-spacer></v-spacer>
    <v-btn density="comfortable" icon="mdi mdi-phone" class="phone mr-2"></v-btn>
    <div>
        <span class="text-caption">Call To</span><br/>
        <span class="text-grey text-caption mr-2">+98 9301274130</span>
    </div>
</v-app-bar>
</template>
<script>
export default{

}
</script>
<style>
.account{
    transition-duration: 0.4s;
}
.account:hover{
    color: orange;
}
.phone{
    background-color: orange !important;
}
</style>