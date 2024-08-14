<template>
    <div class="card">
        <h4>{{ props.title }}</h4>
        <p>{{ props.description }}</p>
    </div>
</template>

<script setup lang="ts">
interface IProps{
    title: string;
    description: string;
}

const props = defineProps<IProps>()
console.log(props)
</script>

<style lang="scss" scoped>
.card{
    padding: 10px;
    border-radius: 7px;
    box-shadow: 1px 1px 10px #937f7f
}
</style>