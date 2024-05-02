
<template>
<v-footer color="#1f1f1f" class="d-flex flex-column">
  <div class="px-4 py-2 bgTop w-100">
    <v-toolbar color="transparent" height="40">
      <span class="mr-2">Refund Policy</span>
      <v-spacer></v-spacer>
      <v-icon>mdi mdi-cash-multiple</v-icon>
      <v-icon>mdi mdi-currency-multiple</v-icon>
      <v-icon>mdi mdi-cash-100</v-icon>

    </v-toolbar>
  </div>
  <div class="d-flex w-100 bgMidum px- pb-10">
    <v-row>
      <v-col cols="12" sm="3">
        <span class="text-caption">Address</span><br/>
      </v-col>
      <v-col cols="12" sm="3">
        <span class="text-caption">Address</span><br/>

      </v-col>
      <v-col cols="12" sm="3">
        <span class="text-caption">Address</span><br/>

      </v-col>
      <v-col cols="12" sm="3">
<h4 class="mt-2"> Location</h4>
<v-img src="" height="150" class="ml-n16"></v-img>
      </v-col>

    </v-row>
  </div>
  <div class="pw-4 py-2 bgTop text-center w-100">
    <v-icon class="mr-2"> mdi mdi-copyright</v-icon>{{ new Date().getFullYear() }}<strong>Sssas</strong>
  </div>
</v-footer>
</template>
<script>
</script>
<style>
.v-footer{
  padding: 0 0 !important;
}
.bgTop{
  background-color: #111111;
}
.bgMidum{
  background-color: #1f1f1f;
}

</style>