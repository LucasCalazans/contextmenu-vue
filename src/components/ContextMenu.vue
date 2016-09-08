<template>
  <ul id="context-menu">
    <context-menu-item @click="newRegister()">
      <img class="context-menu-icon" src="../assets/icon-add.svg" width="12">
      Novo registro
    </context-menu-item>
    <context-menu-item @click="remove()">
      <img class="context-menu-icon" src="../assets/icon-remove.svg" width="10">
      Remover
    </context-menu-item>
    <context-menu-item @click="edit()">
      <img class="context-menu-icon" src="../assets/icon-edit.svg" width="12">
      Ediar
    </context-menu-item>
  </ul>
</template>

<script>
import ContextMenuItem from './ContextMenuItem';

export default {
  components: {
    ContextMenuItem
  },
  methods: {
    newRegister: () => {
      alert('Novo registro');
    },
    remove: () => {
      alert('Remover');
    },
    edit: () => {
      alert('Editar');
    }
  }
}
</script>

<style scoped>

#context-menu {
  top: 0;
  left: 0;
  margin: 0;
  padding: 0;
  display: none;
  list-style: none;
  position: absolute;
  z-index: 2147483647;
  background-color: white;
  border: 1px solid #ebebeb;
  border-bottom-width: 0px;
}

#context-menu.active {
  display: block;
}

.context-menu-icon {
  top: 1px;
  position: relative;
  margin-right: 10px;
}

</style>