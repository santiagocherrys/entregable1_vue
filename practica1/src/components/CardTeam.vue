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
            <div v-if="props.group == '1'" class="image-stack">
                <img src="../assets/images/phineas.jpg" alt="Person 1">
                <img src="../assets/images/ferb.jpg" alt="Person 2">
                <img src="../assets/images/candace.jpg" alt="Person 3">
                <img src="../assets/images/isabella.jpg" alt="Person 4">
            </div>
            <div v-if="props.group == '2'" class="image-stack">
                <img src="../assets/images/amigaCandance.jpg" alt="Person 1">
                <img src="../assets/images/perry.jpg" alt="Person 2">
                <img src="../assets/images/Heinz.png" alt="Person 3">
                <img src="../assets/images/jeremy.jpg" alt="Person 4">
            </div>
            <div class="container2">
                <h3 v-for="(item, index) in props.technology" :class="props.color[index]" class="tag">{{item}}{{  }}</h3>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
interface IProps{
    icon: string;
    title: string;
    description: string;
    group: string
    technology: string[]
    color: string[]
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

//imagenes redondas y juntas
.image-stack {
  display: flex;
  align-items: center;
}

.image-stack img {
  width: 50px; /* Set the desired size of the circles */
  height: 50px;
  border-radius: 50%; /* Make the images circular */
  border: 2px solid white; /* Add a white border */
  object-fit: cover; /* Ensure the image covers the entire circle */
  margin-left: -20px; /* Overlap the images */
  transition: transform 0.3s ease;
}

.image-stack img:first-child {
  margin-left: 0; /* No overlap on the first image */
}

.image-stack img:hover {
  transform: scale(1.1); /* Slightly enlarge on hover */
  z-index: 1; /* Bring the hovered image to the front */
}

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
</style>
