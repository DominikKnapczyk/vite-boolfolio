<template>
  <div class="card">
    <img class="card-img-top" :src="project.image" alt="Card image cap">
    <div class="card-body">
      <h5 class="card-title">{{ project.title }}</h5>
      <p class="card-text">{{ project.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: {
    project: {
      type: Object,
      required: true
    }
  }
};
</script>

<style>
.card {
  width: 18rem;
  margin-bottom: 20px;
}

.card-img-top {
  height: 200px;
  object-fit: cover;
}

.card-title {
  font-size: 20px;
}

.card-text {
  font-size: 16px;
}
</style>
