<template>
    <div>
        <select v-model="selected" @change="$emit('choose', selected)">
            <option value="any">Any</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selected: "any",
        }
    }
}
</script>

<style lang="scss" scoped>
    div {
        display: flex;
        padding-top: 10px;

        select {
            background-color: #2e3a46;
            color: #fff;
        }
    }
    
</style>