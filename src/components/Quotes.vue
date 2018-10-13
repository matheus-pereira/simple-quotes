<template>
    <div class="quotes">
        <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteQuote(index)">
            <p>{{ quote }}</p>
        </app-quote>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    props: ['quotes'],
    components: {
        'app-quote': Quote
    },
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index);
        }
    }
}
</script>

<style>
.quotes {
    margin-top: 20px;
    margin-bottom: 20px;
}
</style>
