<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Users</h1>
        <pre>{{users}}</pre>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Users',

  data: () => ({
    users: [],
  }),
  created() {
    this.load();
  },

  methods: {
    load() {
      fetch('https://jsonplaceholder.typicode.com/users')
        .then((response) => response.json())
        .then((json) => (this.users = json));
    },
  },
};
</script>
