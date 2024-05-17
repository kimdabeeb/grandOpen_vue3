<template>
  <div class="inner">
    <FirstEvent />
    <TabContainer />
  </div>
</template>

<script>
import FirstEvent from './components/event/FirstEvent';
//import TabContainer from './components/TabContainer.vue';

export default {
  name: 'App',
  components: {
    FirstEvent,
    //TabContainer,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
