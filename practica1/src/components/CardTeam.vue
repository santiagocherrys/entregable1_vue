<template>
    <div class="card">
        <div class="container">
            <div class="container2">
                <h3>Hola</h3>
                <h3>Bonyur</h3>
            </div>
            
            <div class="container2">
                <h3>Chao</h3>
                <h3>Adios</h3>
            </div>
        </div>

        <h4>{{ props.title }}</h4>
        <p>{{ props.description }}</p>

        <div class="container">
            <h1>Hola</h1>
            <div class="container2">
                <h3>Chao</h3>
                <h3>Adios</h3>
            </div>
        </div>
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
    height: 150px;
    width: 350px;
    border-radius: 7px;
    box-shadow: 1px 1px 10px #937f7f
}

.container{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.container2{
    display: flex;
    flex-direction: row;
    gap: 10px
}
</style>