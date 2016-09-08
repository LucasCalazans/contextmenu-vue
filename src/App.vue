<template>
  <div id="app" @click="hideContextMenu()" @contextmenu.prevent="showContextMenu()">
    <div>
      <img class="logo" src="./assets/logo.png">
      <h1 class="instructions">Click with right-button on body</h1>
      <context-menu></context-menu>
    </div>
  </div>
</template>

<script>
import ContextMenu from './components/ContextMenu';

export default {
  data: () => {
    return {
      contextMenuWidth: null,
      contextMenuHeight: null
    }
  },
  methods: {
    showContextMenu: function() {
      var menu = document.getElementById("context-menu");
      if(!this.contextMenuWidth || !this.contextMenuHeight) {
        menu.style.visibility = "hidden";
        menu.style.display = "block";
        this.contextMenuWidth = menu.offsetWidth;
        this.contextMenuHeight = menu.offsetHeight;
        menu.removeAttribute("style");
      }

      if((this.contextMenuWidth + this.$event.pageX) >= window.innerWidth) {
        menu.style.left = (this.$event.pageX - this.contextMenuWidth) + "px";
      } else {
        menu.style.left = this.$event.pageX + "px";
      }

      if((this.contextMenuHeight + this.$event.pageY) >= window.innerHeight) {
        menu.style.top = (this.$event.pageY - this.contextMenuHeight) + "px";
      } else {
        menu.style.top = this.$event.pageY + "px";
      }
      
      menu.classList.add('active');
    },
    hideContextMenu: function() {
      document.getElementById("context-menu").classList.remove('active');
    }
  },
  components: {
    ContextMenu
  }
}
</script>

<style>

@font-face {
  font-family: CaviarDreams;
  src: url(assets/CaviarDreams.ttf);
}

html, body, #app {
  margin: 0;
  width: 100%;
  height: 100%;
  display: flex;
  text-align: center;
  align-items: center;
  justify-content: center;
  background-color: #343338;
  font-family: CaviarDreams, Roboto, Tahoma, sans-serif;
}

.logo {
  height: 100px;
}

.instructions {
  color: white;
  display: block;
  font-size: 25px;
}
</style>
