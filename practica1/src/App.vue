<script setup lang="ts">
import { ref } from "vue";
import Card from "@/components/Card.vue"


const page = ref('PROFILE');

const cardsTeams = [
  {title: 'Tittle 1',
    description: 'Description 1'
  },
  {title: 'Tittle 2',
    description: 'Description 2'
  },
  {title: 'Tittle 3',
    description: 'Description 3'
  },
  {title: 'Tittle 4',
    description: 'Description 4'
  },
  {title: 'Tittle 5',
    description: 'Description 5'
  },
  {title: 'Tittle 6',
    description: 'Description 6'
  }
]

const changePage = (newPage: string) =>{
  page.value = newPage;
}

</script>

<template>
  <section>
    <button @click="changePage('PROFILE')">Profile</button>
    <button @click="changePage('TEAM')">TEAM</button>
    <button @click="changePage('PROJECTS')">Projects</button>
    <button @click="changePage('CONNECTIONS')">Connections</button>
  </section>

  <div v-if="page =='PROFILE'">
    <h2>Profile page</h2>
  </div>

  <div v-if="page == 'TEAM'">
    <h2>Team page</h2>
    <div class="container-cards">
      <Card
        v-for="iterator in cardsTeams"
        :title="iterator.title"
        :description="iterator.description"
      />
    </div>
  </div>

  <div v-if="page == 'PROJECTS'">
    <h2>Projects page</h2>
  </div>

  <div v-if="page == 'CONNECTIONS'">
    <h2>Connections page</h2>
  </div>
</template>

<style lang="scss" scoped>
section{
  display: flex;
  gap: 20px;
}

.container-cards{
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
