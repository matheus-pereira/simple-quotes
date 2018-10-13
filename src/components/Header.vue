<template>
    <div class="row">
        <div class="col-sm-12">
            <h3>Quotes Added</h3>
            <div class="progress">
                <div class="progress-bar" :style="{width: (quotesCount / maxQuotes) * 100 + '%'}">
                    {{ quotesCount }} / {{ maxQuotes }}
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quotesCount', 'maxQuotes']
}
</script>
