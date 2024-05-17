<template>
  <div class="tabs flex">
    <!-- <button
      v-for="tab in tabs"
      :key="tab.name"
      @click="activeTab = tab.component"
    >
      {{ tab.name }}
    </button> -->
    <button
      v-for="tab in tabs"
      :key="tab.name"
      :class="{'is-disabled': tab.disabled}"
      @click="changeTab(tab)"
    >
      {{ tab.name }}
    </button>
  </div>
  <div class="tab-content">
    <component :is="activeTab" />
  </div>
</template>
<script>
import FirstEvent from './components/event/FirstEvent.vue';
import SecondEvent from './components/event/SecondEvent.vue';
import ThirdEvent from './components/event/ThirdEvent.vue';
import FourEvent from './components/event/FourEvent.vue';

export default {
  components: {
    FirstEvent,
    SecondEvent,
    ThirdEvent,
    FourEvent,
  },
  data() {
    return {
      tabs: [
        { name: 'FirstEvent', component: FirstEvent, disabled: false, alertMessage: null },
        {
          name: 'SecondEvent',
          component: SecondEvent,
          disabled: true ,
          alertMessage: '7월 22일 오픈 예정입니다!',
        },
        {
          name: 'ThirdEvent',
          component: ThirdEvent,
          disabled: true ,
          alertMessage: '8월 12일 오픈 예정입니다!',
        },
        {
          name: 'FourEvent',
          component: FourEvent,
          disabled: true,
          alertMessage: '오픈 예정입니다!',
        },
      ],
      activeTab: FirstEvent,
    };
  },
  methods: {
    changeTab(tab) {
      if (tab.disabled) {
        alert(tab.alertMessage);
      } else {
        this.activeTab = tab.component;
      }
    }
  },
};
</script>
<style>
.tabs {
  background: url(../assets/tab/bg.jpg) no-repeat center/cover;
  height: 110px;
}

.tabs button {
  padding: 10px;
  cursor: pointer;
}

.is-disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
</style>
