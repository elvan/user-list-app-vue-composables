<template>
  <div class="backdrop" @click="closeDialog"></div>
  <dialog open>
    <header>
      <h2>{{ title }}</h2>
    </header>
    <div>
      <slot></slot>
    </div>
    <menu>
      <button @click="closeDialog">Close</button>
    </menu>
  </dialog>
</template>

<script>
export default {
  props: ['title'],
  emits: ['close'],
  setup(_, context) {
    function closeDialog() {
      context.emit('close');
    }

    return { closeDialog };
  },
};
</script>

<style scoped>
.backdrop {
  z-index: 10;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.75);
}

dialog {
  z-index: 100;
  position: fixed;
  top: 30vh;
  left: calc(50% - 15rem);
  width: 30rem;
  margin: 0;
  padding: 0;
  border: none;
  border-radius: 12px;
  overflow: hidden;
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
}

header {
  width: 100%;
  padding: 1rem;
  color: white;
  background-color: #310131;
}

dialog div {
  padding: 1rem;
}

menu {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 1rem;
}
</style>
