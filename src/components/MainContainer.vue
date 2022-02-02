<template>
    <div class="container">
        <record-box
        v-for="disk in disks"
        :key="disk.title"
        :disk="disk"
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
        disks: Array
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
