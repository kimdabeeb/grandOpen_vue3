<template>
  <div id="tab">
    <div id="intro">
      <p>
        <img src="@/assets/images/01_main.jpg">
      </p>
    </div>
    <RouletteBoard id="roulette_bg" />
    <SnsCopy />
    <SnsUrl />
  </div>
</template>

<script>
import RouletteBoard from '@/components/event/event-function/RouletteBoard';
import SnsCopy from '@/components/event/event-function/SnsCopy';
import SnsUrl from '@/components/event/event-function/SnsUrl';

export default {
  components: {
    RouletteBoard,
    SnsCopy,
    SnsUrl,
  },
};
</script>

<style scoped>
</style>
