<script setup lang="ts">
import { ref } from "vue";
import CardTeam from "@/components/CardTeam.vue"
import CardConnections from "./components/CardConnections.vue";


const page = ref('PROFILE');

const cardsTeams = [
  { icon: 'react_original_logo_icon_146374.svg',
    title: 'React Developers',
    description: 'We dont make assumptions about the rest of your technology stack, so you can develop new features in React',
    group: '1',
    technology: ['React', 'MUI'],
    color: ['morado', 'azul']
  },
  { icon: 'file_type_vue_icon_130078.svg',
    title: 'Vue.js Dev Team',
    description: 'The development o f Vue and its ecosystem in guided by an international team, some of whom have choosen to be featured below',
    group: '2',
    technology: ['Vuejs', 'Developer'],
    color: ['verde', 'rojo']
  },
  { icon: 'adobe_xd_alt_macos_bigsur_icon_190423.png',
    title: 'Creative Designers',
    description: 'A design or product team is more than just the people on it. A team includes the people, the roles they play, and the colaboation they foster',
    group: '1',
    technology: ['Sketch', 'XD'],
    color: ['verde', 'rojo']
  },
  { icon: 'supportteam_lifeguard_9563.png',
    title: 'Support Team',
    description: 'Support your team. Your customer support team is fielding the good, the bad, and the ugly day in and day out.',
    group: '2',
    technology: ['Zendesk'],
    color: ['azul']
  },
  { icon: 'web-svgrepo-com.svg',
    title: 'Digital Marketing',
    description: 'Digital marketing refers to advertising delivered through digital channels sunch a search engines, websites, and mobile apps.',
    group: '1',
    technology: ['Twitter', 'Email'],
    color: ['morado', 'verde']
  },
  { icon: 'google_calendar_logo_icon_159345.svg',
    title: 'Event',
    description: 'Event is defined as a particulr contest which is part of a program of contests. An example of an event is the long jump competition',
    group: '2',
    technology: ['Hubilo'],
    color: ['verde']
  },
  { icon: 'figma_logo_icon_170157.svg',
    title: 'Figma Resources',
    description: 'Explore, install, use, and remix thousands of plugins and files published to the Figma Community by designers and developers.',
    group: '1',
    technology: ['UI/UX', 'Figma'],
    color: ['verde', 'morado']
  },
  { icon: 'react_original_logo_icon_146374.svg',
    title: 'Native Mobile App',
    description: 'React Native lets you create user friendly native apps and doesnt compromise your users experiences. With its robst framework',
    group: '1',
    technology: ['React'],
    color: ['morado']
  },
  { icon: 'HTML5_icon-icons.com_67090.svg',
    title: 'Only Beginners',
    description: 'Learn the basics of how websites work, front-end vs back-end and using a code editor. Learn basic HTML, CSS, and ...',
    group: '2',
    technology: ['CSS', 'HTML'],
    color: ['azul', 'rojo']
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
        :icon="iterator.icon"
        :title="iterator.title"
        :description="iterator.description"
        :group="iterator.group"
        :technology="iterator.technology"
        :color="iterator.color"
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
