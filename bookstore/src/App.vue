<template>
  <div class="app" :class="mode" >
    <Header :mode="mode" @toggle="toggle"/>
    <Content :mode="mode"/>
  </div>
</template>

<script>
import Header from './components/BookstoreHeader'
import Content from './components/BookstoreContent'
export default {
  name: 'App',
  data() {
    return {
      mode:'light',
    }
  },
  components: {
    Header,
    Content
  },
  methods: {
    toggle () {
      if(this.mode === 'dark') {
        this.mode ='light'
      } else {
        this.mode ='dark'
      }
    },
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}

.app {
  width: 100vw;
  min-height: 100vh;
  background: #f1ffff;
  color: #152028;
  transition: background 0.3s ease-in-out;
}
.dark {
  background: #1b2432;
  color: #f3f3f3;
}
.pagination {
  margin-bottom: 0;
  padding: 40px;
}
.page-link {
  background:  #f1ffff !important;
  color: black !important;
  border:none !important;
}
.page-item.active .page-link {
  background-color: #3498db !important;
  color: #fff !important;
}
.dark .page-link {
  background: #1b2432 !important;
  color: #fff !important;
}




</style>