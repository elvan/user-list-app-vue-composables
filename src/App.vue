<template>
  <main>
    <add-user></add-user>
    <delete-user></delete-user>
  </main>
</template>

<script>
import AddUser from './components/AddUser.vue';
import DeleteUser from './components/DeleteUser.vue';

export default {
  components: {
    AddUser,
    DeleteUser,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

main {
  width: 40rem;
  margin: 3rem auto;
}

section {
  margin: 2rem auto;
  padding: 1rem;
  border: 1px solid #ccc;
  border-radius: 12px;
}

button {
  padding: 0.5rem 1.5rem;
  border: 1px solid #310131;
  border-radius: 8px;
  color: white;
  font: inherit;
  cursor: pointer;
  background-color: #310131;
}

button:hover,
button:active {
  border-color: #770e77;
  background-color: #770e77;
}
</style>
