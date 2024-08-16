<template>
    <div class="card">
        <img src="../assets/images/icons/dots-vertical-svgrepo-com.svg" class="left" alt="">
        <img :src="getImageUrl()" class="rounded"  alt="">
        <span>{{ props.name }}</span>
        <p>{{ props.profesion }}</p>
        <div class="centerTech">
            <h3 v-for="(item, index) in props.technology" :class="props.color[index]" class="tag">{{item}}</h3>
        </div>
        <div class="centerNumbers">
            <div class="center">
                <b>{{ props.projects }}</b>
                <p>Projects</p>
            </div>
            <div class="center">
                <b>{{ props.tasks }}</b>
                <p>Tasks</p>
            </div>

            <div class="center">
                <b>{{ props.connections }}</b>
                <p>Connections</p>
            </div>
           
        </div>
            <div class="centerTech">
                <h3 v-if="props.connected == '1'" class="tag connected">Connected</h3>
                <h3 v-if="props.connected == '0'" class="tag gris">Connect</h3>
                <img src="../assets/images/icons/letter-svgrepo-com.svg" class="tag imagen" alt="">
            </div>
       
    </div>
    
    

</template>

<script setup lang="ts">
interface IProps{
    image: string;
    name: string;
    profesion: string;
    technology: string[]
    color: string[]
    projects: string
    tasks: string
    connections: string
    connected: string
}

const props = defineProps<IProps>()
console.log(props)

function getImageUrl() {
  // This path must be correct for your file
  return new URL(`../assets/images/${props.image}`, import.meta.url)
}
</script>

<style lang="scss" scoped>
.card{
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
    height: 300px;
    width: 350px;
    border-radius: 7px;
    box-shadow: 1px 1px 10px #937f7f
}

.rounded {
    width: 90px; /* Set the desired size of the circles */
    height: 90px;
    border-radius: 50%;
    object-fit: cover; /* Ensure the image covers the entire circle */
}

.centerTech{
    display: flex;
    flex-direction: row;
    gap: 10px;
}

.centerNumbers{
    display: flex;
    flex-direction: row;
    gap: 70px;
}

.center{
    text-align: center;
}

//color and squared of the technology
//color and squared of the technology
.tag {
  margin: 12px 0;
  padding: 5px 10px;
  border-radius: 8px;
  font-size: 14px;
  font-weight: 500;
  color: white;
  text-align: center;
}

.morado {
  background-color: #e0d7fb; 
  color: #7b5af8; 
}

.verde {
  background-color: #d6f5dc; /* Light green background */
  color: #52c771; /* Darker green text */
}

.rojo {
  background-color: #fcd6d6; /* Light pink background */
  color: #ff6b6b; /* Darker pink/red text */
}

.azul {
  background-color: #d2f7f6; 
  color: #00c2cc; 
}

.gris{
    background-color: gray;
}

.connected{
    background-color: #7b5af8; 
    color: white;
}

.imagen{
    width: 40px;
    background-color: gray;
}

.left{
    width: 30px;
    margin-left: 290px;
}

</style>