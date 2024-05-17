<template>
  <div class="step3">
    <h2>step 3</h2>
    <p>
      공유한 게시글 주소 붙여넣고 <br>
      응모하기 클릭하면 끝!<br>
      중복 참여도 가능합니다.
    </p>
    <input
      v-model="snsUrl"
      placeholder="공유한 SNS게시물 주소"
    >
    <button @click="checkValidURL">
      응모하기
    </button>
  </div>
</template>
<script>
import { ref } from 'vue';

export default {
  setup() {
    const snsUrl = ref('');
    function checkValidURL() {
      const validURLPattern =
        /(http(s)?:\/\/.)?(www\.)?[-a-zA-Z0-9@:%._+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_+.~#?&//=]*)/g;
      if (!validURLPattern.test(snsUrl.value)) {
        alert('응모되었습니다.');
      } else {
        alert('응모기간이 아닙니다.');
      }
    }
    return {
      snsUrl,
      checkValidURL,
    };
  },
};
</script>
<style lang=""></style>
