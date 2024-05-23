<template>
  <div class="caution-container">
    <div class="caution">
      <div class="caution_title flex">
        <p><img src="@/assets/img/ico_info.png" /> 유의사항</p>
        <button
          type="button"
          class="btn btn--primary btn--viewing-status"
          @click="toggleBox"
        >
          <i class="ic ic--dropdown" :class="{ 'is-open': isOpen }"></i>
        </button>
      </div>
      <ul class="caution_txt" v-if="isOpen">
        <li>당첨자 발표 : 2024년 7월 24일 (수)</li>
        <li>적립금 사용기간 : 지급일로부터 30일 이내</li>
        <li>중복 참여할 수 있지만, 적립금은 ID당 1회 지급됩니다.</li>
        <li>
          비정상적이거나 불법적인 방법으로 이벤트에 참여한 경우, 당첨자 선정
          대상에서 제외될 수 있으며 <br /><span
            >당첨 후에도 취소될 수 있습니다.</span
          >
        </li>
        <li>
          본 이벤트는 당사의 사정에 따라 별도 고지 없이 변경 또는 종료 될 수
          있습니다.
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
import { ref } from 'vue';
export default {
  setup() {
    const isOpen = ref(false);
    const toggleBox = () => {
      isOpen.value = !isOpen.value;
    };
    return {
      isOpen,
      toggleBox,
    };
  },
};
</script>
<style scoped>
.caution-container {
  width: 70%;
  overflow: hidden;
}

.caution {
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 20px;
  padding: 1.5rem 2rem;
  box-sizing: border-box;
}

.caution.is-open {
  opacity: 1;
}

.caution_title {
  justify-content: space-between;
}

.caution_txt {
  overflow: hidden;
  max-height: 0;
  transition: max-height 0.3s ease-in-out;
  /* opacity: 0;
  margin-top: 1.25rem;
  padding-top: 1.25rem;
  border-top: 1px solid rgba(0, 0, 0, 0.1); */
}

.caution_txt li {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.caution.is-open .caution_txt {
  opacity: 1;
}

.caution_txt li:not(:last-child) {
  margin-bottom: 1rem;
}

.caution_txt.is-open {
  max-height: 300px;
}

.is-open .ic--dropdown::before {
  transform: translateY(-5px) rotate(-135deg);
}
</style>
