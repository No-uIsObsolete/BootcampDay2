<template>
    <div>
        <button @click = "pobierzWpisy">refresh</button>
        siema blog!
        {{ wpisy }}
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
            this.wpisy = await Day2_backend.odczytaj_wpisy()
        }
    },
}
</script>