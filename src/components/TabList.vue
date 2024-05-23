<template>
  <ul class="tablist flex">
    <li>
      <a @click="changeTab('FirstComponent')">
        <div><span>01</span><br />특별 선물 1탄</div>
      </a>
    </li>
    <li>
      <a @click="showAlert('7월 22일 오픈 예정입니다!')">
        <div><span>02</span><br />특별 선물 2탄</div>
      </a>
    </li>
    <li>
      <a @click="showAlert('8월 12일 오픈 예정입니다!')">
        <div><span>03</span><br />특별 선물 3탄</div>
      </a>
    </li>
    <li>
      <a @click="showAlert('오픈 예정입니다!')">
        <div>
          <span>04</span><br />
          인터넷 영풍문고<br />어떻게 달라졌을까?
        </div>
      </a>
    </li>
    <!-- <li>
      <a @click="changeTab('SecondComponent')"
        ><span>02</span><br />특별 선물 2탄</a
      >
    </li>
    <li>
      <a @click="changeTab('ThirdComponent')"
        ><span>03</span><br />특별 선물 3탄</a
      >
    </li>
    <li>
      <a @click="changeTab('LastComponent')"
        ><span>04</span><br />인터넷 영풍문고<br />어떻게 달라졌을까?</a
      >
    </li> -->
  </ul>
  <component :is="activeTab" />
</template>
<script>
import { shallowRef } from 'vue';
import FirstComponent from './event/FirstComponent';
import SecondComponent from './event/SecondComponent.vue';
import ThirdComponent from './event/ThirdComponent.vue';
import LastComponent from './event/LastComponent.vue';

export default {
  components: {
    FirstComponent,
    SecondComponent,
    ThirdComponent,
    LastComponent,
  },
  data() {
    return {
      activeTab: shallowRef(FirstComponent),
    };
  },
  methods: {
    changeTab(tabName) {
      this.activeTab = tabName;
    },
    showAlert(message) {
      alert(message);
    },
  },
};
</script>
<style scoped>
.tablist {
  width: 100%;
  min-height: 110px;
  background: url('@/assets/img/tab/bg.jpg') no-repeat center/cover;
  justify-content: center;
}

.tablist li:first-child a {
  min-height: 110px;
  background: #fff;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.tablist li:first-child a::after {
  content: '';
  display: block;
  width: 9px;
  height: 9px;
  border-radius: 50%;
  background: tomato;
  margin: 10px auto 0;
}

.tablist li:first-child a {
  color: black;
  font-weight: 600;
}

.tablist li > a {
  display: inline-block;
  padding: 0 2rem;
  box-sizing: border-box;
  text-align: center;
  font-size: 1.35rem;
  font-weight: 500;
  letter-spacing: -1px;
  color: rgba(255, 255, 255, 0.5);
}

.tablist li:last-child > a {
  font-size: 1.2rem;
  line-height: 1.3;
}

.tablist li a span {
  letter-spacing: 0.5px;
  line-height: 1.6;
  font-size: 1.125rem;
  font-family: Futura;
}

.tablist li:not(:last-child) {
  border-right: 1px solid rgba(255, 255, 255, 0.3);
}
</style>
