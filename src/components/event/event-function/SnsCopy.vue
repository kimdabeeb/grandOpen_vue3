<template>
  <div class="step2">
    <h2>step 2</h2>
    <p>
      개인 SNS에 이벤트를 홍보해주세요. <br>
      필수 태그 + 이벤트 대표 이미지 함께 올리고<br>
      공개 계정인지 꼭 확인해주세요!
    </p>
    <p class="clipboard">
      #영풍문고 #그랜드오픈 #리뉴얼 #랜선집들이 @ypbooks
    </p>
    <input
      ref="inputEl"
      type="hidden"
      value="#영풍문고 #그랜드오픈 #리뉴얼 #랜선집들이 @ypbooks"
      @focus="$event.target.select()"
    >
    <button @click="handleCopy">
      필수 태그 복사하기
    </button>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const inputEl = ref(null);
    const handleCopyForIE = () => {
      inputEl.value.setAttribute('type', 'text');
      inputEl.value.select();
      document.execCommand('copy');
      inputEl.value.setAttribute('type', 'hidden');
      alert('execCommand를 통해 내용이 복사되었습니다');
    };

    const handleCopy = () => {
      if (inputEl.value === null) {
        return;
      }
      if (!navigator.clipboard) {
        handleCopyForIE();
        return;
      }
      navigator.clipboard.writeText(inputEl.value.value).catch((e) => {
        console.log(e.message);
        handleCopyForIE();
      });
    };

    return {
      inputEl,
      handleCopy,
    };
  },
};
</script>

<style scoped>
</style>
