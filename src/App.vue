<template>
  <div class="container">
    <h1>Boolfolio</h1>
    <div class="card-container">
      <project-card v-for="(project, index) in projects" :key="index" :project="project"></project-card>
    </div>
  </div>
</template>



<script>
import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue';

export default {
  name: 'App',
  components: {
    ProjectCard
  },
  data() {
    return {
      projects: []
    }
  },
  created() {
    axios.get('http://localhost:8000/projects')
      .then(response => {
        this.projects = response.data;
        console.log(this.projects);
      })
      .catch(error => console.log(error));
  }
};
</script>

<style>
.container {
  max-width: 800px;
  margin: 0 auto;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
}

.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style>

