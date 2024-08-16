<template>
    <div class="card">
        <div class="container">
            <div class="container2">
                <img :src="getImageUrl()"  alt="">
                <h4>{{ props.title }}</h4>

            </div>
            
            <div class="container2">
                <img src="../assets/images/icons/star-svgrepo-com.svg" alt="">
                <img src="../assets/images/icons/dots-vertical-svgrepo-com.svg" alt="">
            </div>
        </div>

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
    icon: string;
    title: string;
    description: string;
}

const props = defineProps<IProps>()
console.log(props)

function getImageUrl() {
  // This path must be correct for your file
  return new URL(`../assets/images/icons/${props.icon}`, import.meta.url)
}
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
    //padding: 0 10px;
    //gap: 80px;
}

.container2{
    display: flex;
    flex-direction: row;
    gap: 5px
}

//this is cause the space in the string are generating a \n in the space
.container2 h4 {
    white-space: nowrap;
}

img{
    width: 20px;
}
</style>
