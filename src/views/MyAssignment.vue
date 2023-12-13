<!-- Assignments.vue -->
<script>
export default {
  data() {
    let assignments = [
      { name: "Web Application", completed: false },
      { name: "Desktop with C#", completed: true },
      { name: "Marketing Project", completed: false },
      { name: "Vue Projects", completed: false },
    ];

    for (let i = 0; i < assignments.length; i++) {
      assignments[i].id = i + 1;
    }
    return {
      assignments: assignments,
    };
  },
  computed: {
    updateAssignment() {
      return (status) => {
        return this.assignments.filter((a) => a.completed == status);
      };
    },
  },
};
</script>
<template>
  <div>
    <div>
      <h2>Unfinished Assignments</h2>
      <ul v-for="data in updateAssignment(false)" :key="data">
        <li>
          {{ data.id }} : &nbsp; {{ data.name }}
          <input type="checkbox" v-model="data.completed" />
        </li>
      </ul>
    </div>
    <div>
      <h2>Finished Assignments</h2>
      <ul v-for="data in updateAssignment(true)" :key="data">
        <li>
          {{ data.id }} : &nbsp; {{ data.name }}
          <input type="checkbox" v-model="data.completed" />
        </li>
      </ul>
    </div>
  </div>
</template>
