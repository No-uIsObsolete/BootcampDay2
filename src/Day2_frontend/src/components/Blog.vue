<template>
    <div>
        <button @click = "pobierzWpisy">refresh</button>
        siema blog!
        {{ wpisy }}
        <input v-model="nowyBlog" type="text">
        <button @click = "dodajWpisy">dodaj</button>


    </div>
</template>

 <script>
import { Day2_backend } from 'declarations/Day2_backend/index';

export default {
    data() {
        return {
            wpisy: []
        }
    },
    methods: {
        async pobierzWpisy() {
            this.wpisy = await Day2_backend.dodaj_wpisy(nowyBlog)
        },

        async dodajWpisy() {
            this.wpisy = await Day2_backend.odczytaj_wpisy()
        }
    },
}
</script>