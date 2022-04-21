<template>
    <div class="result">
        <div class="title">{{results[resultIndex].title}}</div>
        <div class="desc">
        {{results[resultIndex].desc}}
        </div>
    </div>
</template>

<script>
export default {
    name: "ResultsVue",
    props: ['totalCorrect', 'results'],
    computed: {
        resultIndex() {
            let index = 0;
            this.results.forEach((item, ind) => {
                if(item.min <= this.totalCorrect && item.max >= this.totalCorrect) {
                    index = ind; 
                }
            });
            return index;
        }
    }
}
</script>

