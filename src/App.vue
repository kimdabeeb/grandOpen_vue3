<template>
  <div class="intro inner">
    <img src="@/assets/img/01_main.jpg" />
    <TabList />
  </div>
</template>

<script>
import TabList from './components/TabList';
export default {
  name: 'App',
  components: {
    TabList,
  },
};
</script>

<style>
@import './styles/common.css';
@import './styles/event.css';
</style>
