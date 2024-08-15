<script setup lang="ts">
import { ref } from "vue";
import CardTeam from "@/components/CardTeam.vue"
import CardConnections from "./components/CardConnections.vue";


const page = ref('PROFILE');

const cardsTeams = [
  {title: 'React Developers',
    description: 'We dont make assumptions about the rest of your technology stack, so you can develop new features in React'
  },
  {title: 'Vue.js Dev Team',
    description: 'The development o f Vue and its ecosystem in guided by an international team, some of whom have choosen to be featured below'
  },
  {title: 'Creative Designers',
    description: 'A design or product team is more than just the people on it. A team includes the people, the roles they play, and the colaboation they foster'
  },
  {title: 'Support Team',
    description: 'Support your team. Your customer support team is fielding the good, the bad, and the ugly day in and day out.'
  },
  {title: 'Digital Marketing',
    description: 'Digital marketing refers to advertising delivered through digital channels sunch a search engines, websites, and mobile apps.'
  },
  {title: 'Event',
    description: 'Event is defined as a particulr contest which is part of a program of contests. An example of an event is the long jump competition'
  },
  {title: 'Figma Resources',
    description: 'Explore, install, use, and remix thousands of plugins and files published to the Figma Community by designers and developers.'
  },
  {title: 'Native Mobile App',
    description: 'React Native lets you create user friendly native apps and doesnt compromise your users experiences. With its robst framework'
  },
  {title: 'Only Beginners',
    description: 'Learn the basics of how websites work, front-end vs back-end and using a code editor. Learn basic HTML, CSS, and ...'
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
      <CardTeam
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
    <CardConnections />
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
