<template>
    <h1>Ini Login Page {{ isShow }} </h1>

    <v-btn
      depressed
      color="primary"
      @click="increment"
    >
      +
    </v-btn>

    <v-btn
      depressed
      color="error"
      @click="decrement"
    >
      -
    </v-btn>

    <h2>Counter: {{ gelas.count }} </h2>

    <p v-for="element in books" :key="element.id">
        
        {{ element.title }} 

        <v-btn
            depressed
            color="primary"
            @click="deleteItem(element.id)"
            >
            Delete
            </v-btn>
    
    </p>

    <p>{{ publishedBooksMessage }}</p>

    <div class="static" :class="{ active: isActive, 'red': hasError }"> ok oc</div>

    <v-btn
      depressed
      color="primary"
      @click="triggerStyle"
    >
      Trigger
    </v-btn>

    <v-btn
      depressed
      :color="{primary: isActive, danger: !isActive}"
      style="text-danger"
    >
      Class Style Binding
    </v-btn>

</template>
<script>
export default {
    name: "Login",
    // data() {
    //     return {
    //         isShow: false
    //     }
    // },
    data: () => ({
        isActive: true,
        hasError: false,
        gelas: {
            count: 0
        },
        books: [
            {
                id: 1,
                title: 'Vue 2 - Advanced Guide'
            },
            {
                id: 2,
                title: 'Vue 3 - Basic Guide'
            },
            {
                id: 3,
                title: 'Vue 4 - The Mystery'
            },
        ]
    }),
    methods: {
        increment() {
            this.gelas.count++
        },
        decrement() {
            this.gelas.count--
        },
        triggerStyle() {
            this.isActive = !this.isActive;
            this.hasError = !this.hasError;
        },
        deleteItem(id) {
            console.log("id : ", id);
        }
    },
    computed: {
        // a computed getter
        publishedBooksMessage() {
        // `this` points to the component instance
            return this.books.length > 0 ? "oh ini benar tampilin datanya" : "ini harusnya ga tampil karena kosong";
        }
    }
}
</script>