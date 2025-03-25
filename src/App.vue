<script setup>
import { ref, computed } from "vue";


const showWelcome = ref(true);

const projects = ref([
  { id: 1, name: "Vue Blog App" },
  { id: 2, name: "E-commerce Website" },
]);

const projectCount = computed(() => projects.value.length);

const counter = ref(0);



</script>

<template>
  <div>
    <button @click="showWelcome = !showWelcome">Toggle Welcome</button>
    <p v-if="showWelcome">Welcome to My Personal Website!</p>

    <section>
      <h1>Welcome to My Portfolio</h1>
      <p>Hello! I'm a Vue 3 developer.</p>
    </section>


    <section>
    <h2>Projects ({{ projectCount }})</h2>
    <p v-if="projects.length === 0">No projects available.</p>
    <ul>
      <li v-for="project in projects" :key="project.id">
        {{ project.name }}
      </li>
    </ul>
  </section>

    
    
  <section>
    <h2>Counter</h2>
    <p>Visitor count: {{ counter }}</p>
    <button @click="counter++">Increase Count</button>
  </section>


  <section>
    <h2>Contact Me</h2>
    <form>
      <label>Name:</label>
      <input type="text" v-model="name" />
      
      <label>Email:</label>
      <input type="email" v-model="email" />
      
      <button type="submit">Submit</button>
    </form>
  </section>

  </div>
</template>

