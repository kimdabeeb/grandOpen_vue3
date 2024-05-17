<template>
  <div id="roulette_bg">
    <Roulette
      ref="wheel"
      :key="rouletteKey"
      :items="items"
      indicator-position="top"
      display-shadow
      base-display
      size="550"
      base-background="#dedede"
      easing="bounce"
      @click="launchWheel"
      @wheel-start="wheelStartedCallback"
      @wheel-end="wheelEndedCallback"
    />
  </div>
</template>

<script>
import { Roulette } from 'vue3-roulette';

export default {
  components: {
    Roulette,
  },
  data() {
    return {
      items: [
        {
          id: 1,
          name: '100원',
          htmlContent: '100원',
          textColor: '',
          background: '',
        },
        {
          id: 2,
          name: '3천원',
          htmlContent: '3천원',
          textColor: '',
          background: '',
        },
        {
          id: 3,
          name: '300원',
          htmlContent: '300원',
          textColor: '',
          background: '',
        },
        {
          id: 4,
          name: '3만원',
          htmlContent: '3만원',
          textColor: '',
          background: '',
        },
      ],
    };
  },
  methods: {
    launchWheel() {
      this.rouletteKey += 1;
      setTimeout(() => this.$refs.wheel.launchWheel(), 0);
    },
    wheelStartedCallback() {
      console.log('wheelStartedCallback');
    },
    wheelEndedCallback(evt) {
      console.log(evt);
    },
  },
};
</script>

<style scoped>
#roulette_bg {
  background: url('@/assets/images/02_roulett_bg.jpg') no-repeat center/cover;
  width: 100%;
  height: 1460px;
  position: relative;
}

.wheel-container {
  position: absolute;
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%) !important;
}

.wheel-base-container .wheel-base {
  width: 160px !important;
  height: 160px !important;
}

.wheel-base-container {
  width: 160px !important;
  height: 160px !important;
}

#roulette_btn {
  background: url('@/assets/button/btn_roulette.png') no-repeat center/cover;
}
</style>
