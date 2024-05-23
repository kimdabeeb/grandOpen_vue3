<template>
  <div class="roulette_box">
    <Roulette
      ref="wheel"
      :items="items"
      display-indicator
      indicator-position="top"
      base-display
      :baseSize="180"
      :size="600"
      easing="bounce"
      @click="launchWheel"
      @wheel-start="wheelStartedCallback"
      @wheel-end="wheelEndedCallback"
    >
      <template #baseContent>
        <div><img src="@/assets/img/btn/btn_roulette.png" /></div>
      </template>
    </Roulette>

    
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
          htmlContent:
            '적립금 <br> <span class="num">100</span><span class="str">원</span>',
          background: '#fff',
        },
        {
          id: 2,
          name: '3천원',
          htmlContent:
            '적립금 <br> <span class="num">3,000</span><span class="str">원</span>',
          background: '#eee',
        },
        {
          id: 3,
          name: '300원',
          htmlContent:
            '적립금 <br> <span class="num">300</span><span class="str">원</span>',
          background: '#fff',
        },
        {
          id: 4,
          name: '3만원',
          htmlContent:
            '적립금 <br> <span class="num">30,000</span><span class="str">원</span>',
          background: '#eee',
        },
      ],
    };
  },
  methods: {
    launchWheel() {
      this.rouletteKey += 1;
      setTimeout(() => this.$refs.wheel.launchWheel(), 0);
    },
    // launchWheel() {
    //   this.$refs.wheel.launchWheel();
    // },
    wheelStartedCallback() {
      console.log('wheelStartedCallback');
    },
    wheelEndedCallback(evt) {
      console.log(evt);
    },
  },
};
</script>

<style>
.roulette_box {
  position: relative;
  margin: 2.5rem auto 4rem;
}
.roulette_box button {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
}

.wheel-container {
  padding: 8px;
  background: #f9f9f9;
  border: 6px solid;
}

.wheel-container-indicator:before {
  left: 50%;
  top: 0;
}

.wheel .content {
  left: -109% !important;
  padding-top: 4rem !important;
}

.wheel .content > span {
  font-size: 1.7rem;
  font-weight: bold;
}

.wheel .content > span > span.num {
  font-size: 2.2rem;
  letter-spacing: -1.8px;
}

.wheel .content > span span.str {
  font-size: 1.4rem;
  font-weight: 600;
}

.wheel-item {
  border: none !important;
}

.wheel-base-container {
  border: none !important;
}
</style>
