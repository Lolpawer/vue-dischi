<template>
    <div class="container">
        <record-box
        v-for="disc in discs"
        :key="disc.title"
        :disc="disc"
        />
    </div>
</template>

<script>
import RecordBox from './RecordBox.vue'

export default {
    components: {
        RecordBox
    },
    props: {
        discs: Array
    }
}
</script>

<style lang="scss" scoped>
    .container {
        width: 1200px;
        display: flex;
        flex-wrap: wrap;
        padding: 10px 0;
    }

</style>
