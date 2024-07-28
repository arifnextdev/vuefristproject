<script>
export default {
  data() {
    return {
      name: "Ahammad shiekh",
      status: "pending",
      tasks: ["Task One", "Task Two", "Task Three"],
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === "active") {
        this.status = "pending";
      } else if (this.status === "pending") {
        this.status = "UnActive";
      } else {
        this.status = "active";
      }
    },
  },
};
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is Active</p>
  <p v-else-if="status === 'pending'">user is pending</p>
  <p v-else="status">User is UnActive</p>

  <h1>Tasks:</h1>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <button v-on:click="toggleStatus">Change Status</button>
</template>

<style scoped>
h1 {
  color: red;
}

p {
  color: white;
}
</style>
