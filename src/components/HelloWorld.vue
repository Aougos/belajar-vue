<template>
  <v-container>
    <v-row class="text-center">
      <v-col v-for="greeting in greetings" :key="greeting" cols="12" sm="6" md="4">
        {{ greeting }} test
      </v-col>
    </v-row>
    <v-btn @click="onClick">
      Click me
    </v-btn>
    <div v-for="c in customers" :key="c.id">
      <Customer
        v-show="c.id != 1"
        :name="c.name"
        :age="c.age"
      />
    </div>
  </v-container>
</template>

<script>
import Customer from './Customer'

export default {
  name: 'HelloWorld',

  components: {
    Customer,
  },

  mounted() {

  },

  data: () => ({
    greetings: ["Hello", "Goodbye", "Hola"],
    customers: [
      { id: 1, name: "Joko", age: 20 },
      { id: 2, name: "Budi", age: 20 },
      { id: 3, name: "Tono", age: 20 },
      { id: 4, name: "Tina", age: 20 },
      { id: 5, name: "Tini", age: 20 },
      { id: 6, name: "Susi", age: 20 },
      { id: 7, name: "Adhi", age: 20 },
    ],
  }),

  methods: {
    onClick() {
      const newCustomers = this.customers.map(c => ({ ...c, age: c.age * 2}))
      this.customers = newCustomers

    /* Contoh update data ke API
      await updateData(newCustomers) // Kirim data ke backend

      this.customers = await getData()
      */
    },
    async fetchData() {
      // bikin request ke api
      // this.customers = await requestKeApi()

      // const newCustomers = this.customers.map(c => ({ ...c, age: c.age * 2}))
    }
  }
}
</script>

<style>
.test {
  height: 200px;
  width: 200px;
  background-color: red;
}
</style>