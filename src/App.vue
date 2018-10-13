<template>
    <div class="container">
        <app-header :quotesCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quotes :quotes="quotes" @quoteDeleted="deleteQuote"></app-quotes>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info" role="alert">Info: Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import NewQuote from './components/NewQuote.vue';
import Quotes from './components/Quotes.vue';

export default {
    data: function() {
        return {
            quotes: ['Just a Quote to start with something!'],
            maxQuotes: 10
        }
    },
    components: {
        'app-header': Header,
        'app-new-quote': NewQuote,
        'app-quotes': Quotes
    },
    methods: {
        newQuote(quote) {
            if (this.quotes.length >= this.maxQuotes) {
                return alert('Too many Quotes! Delete some before adding new ones!');
            }
            this.quotes.push(quote);
        },
        deleteQuote(index) {
            this.quotes.splice(index, 1);
        }
    }
}
</script>
