<template>
    <div class="card">
        <img src="../assets/images/dexter.png" class="rounded" alt="">
    </div>
    <div class="card">
        <img src="../assets/images/dexter.png" class="rounded" alt="">
    </div>
    <h2>Desde Conexion</h2>
    <div class="card">
        <img src="../assets/images/dexter.png" class="rounded" alt="">
        <div class="image-stack">
        <img src="../assets/images/phineas.jpg" alt="Person 1">
        <img src="../assets/images/ferb.jpg" alt="Person 2">
        <img src="../assets/images/candace.jpg" alt="Person 3">
        <img src="../assets/images/isabella.jpg" alt="Person 4">
        </div>

    </div>
    <div class="card">
        <img src="../assets/images/dexter.png" class="rounded" alt="">
        <div class="image-stack">
        <img src="../assets/images/amigaCandance.jpg" alt="Person 1">
        <img src="../assets/images/perry.jpg" alt="Person 2">
        <img src="../assets/images/Heinz.png" alt="Person 3">
        <img src="../assets/images/jeremy.jpg" alt="Person 4">
        </div>

    </div>

</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>
.card{
    padding: 10px;
    height: 150px;
    width: 350px;
    border-radius: 7px;
    box-shadow: 1px 1px 10px #937f7f
}

.rounded {
  border-radius: 50%;
  width: 80px;
}

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

</style>