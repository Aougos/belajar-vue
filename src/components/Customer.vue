<template>
  <div>
    <v-row>
      <v-col cols="12" sm="6" md="4" class="customer-name">
        name: {{ name }}
      </v-col>
      <v-col cols="12" sm="6" md="4" class="customer-age">
        age: {{ age }}
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Customer",

  props: {
    name: String,
    age: Number,
  }
}
</script>

<style>
.customer-name {
  color: red;
}
.customer-age {
  color: green;
}
</style>