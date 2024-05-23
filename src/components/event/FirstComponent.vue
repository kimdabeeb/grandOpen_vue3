<template>
  <div class="gr_wrapp">
    <!-- section1 s -->
    <div class="sec_1 flex-column">
      <p><img src="@/assets/img/txt/02_roulett_tit.png" /></p>
      <Roulette />
      <div class="caution_box">
        <div class="caution flex-column">
          <div class="caution_title flex">
            <p><img src="@/assets/img/ico_info.png" /> 유의사항</p>
            <button
              type="button"
              :class="[
                'btn btn--primary btn--viewing-status',
                { 'is-open': isOpen },
              ]"
              @click="toggleCaution"
            >
              <i class="ic ic--dropdown"></i>
            </button>
          </div>

          <ul class="caution_txt" v-if="isOpen">
            <li>적립금 사용 기간 : 발급 당일 (이후 자동 소멸)</li>
            <li>
              본 이벤트는 마케팅 수신 동의를 유지한 고객님을 대상으로 1일 1회
              참여가 가능합니다.
            </li>
            <li>
              본 이벤트는 회원대상 혜택이며 비회원인 경우 가입 후 참여
              가능합니다.
            </li>
            <li>
              이벤트에 참여하신 고객님은 개인정보이용에 동의한 것으로
              간주합니다.
            </li>
            <li>
              수집된 정보는 이벤트 운영, 쿠폰 발송 등 홍보 업무에만 활용되며 그
              외의 목적으로 고객의 정보를 이용하지 않습니다.
            </li>
            <li>
              본 이벤트는 당사의 사정에 따라 별도 고지 없이 변경 또는 종료될 수
              있습니다.
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- section2 s -->
    <div class="sec_2 flex-column">
      <p><img src="@/assets/img/03_event_coupon_con.jpg" /></p>
      <div class="caution_box">
        <div class="caution">
          <div class="caution_title flex">
            <p :class="{ 'is-open': isOpen }">
              <img src="@/assets/img/ico_info.png" /> 유의사항
            </p>
            <button
              type="button"
              :class="[
                'btn btn--primary btn--viewing-status',
                { 'is-open': isOpen },
              ]"
              @click="toggleCaution"
            >
              <i class="ic ic--dropdown"></i>
            </button>
          </div>
          <ul class="caution_txt" v-if="isOpen">
            <li>
              본 이벤트는 해당 기간 내 본인인증을 완료한 ID에 한해 최초 1회만
              발급됩니다.
            </li>
            <li>본 이벤트는 본인인증완료 시점을 기준으로 자동 참여 됩니다.</li>
            <li>선착순 300명 한정으로, 별도의 고지 없이 종료될 수 있습니다.</li>
            <li>이벤트 간 중복 당첨이 가능합니다.</li>
            <li>적립금 사용기간 : 지급일로부터 30일 이내</li>
            <li>
              비정상적이거나 불법적인 방법으로 이벤트에 참여한 경우, 당첨자 선정
              대상에서 제외될 수 있으며 당첨 후에도 취소될 수 있습니다.
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- section3 s -->
    <div class="sec_3 flex-column">
      <p><img src="@/assets/img/04_event_sns_con.jpg" /></p>
      <div class="sns_caution flex">
        <p><img src="@/assets/img/txt/04_event_sns_txt_01.png" /></p>
        <div class="sns_caution_info">
          <ul>
            <li>
              <p><img src="@/assets/img/txt/04_event_sns_txt_02.png" /></p>
            </li>
            <li>
              <!-- <button type="button" @click="showModal = true" class="show_img">
                <img src="@/assets/img/btn/btn_1.png" />
              </button>
              <div v-show="showModal" class="modal">
                <div class="modal-content">
                  <p><img src="@/assets/img/popUpImg.jpg" /></p>
                  <button @click="showModal = false">Close</button>
                </div>
              </div> -->
              <div>
                <button type="button" @click="openPopup" class="show_img">
                  <img src="@/assets/img/btn/btn_1.png" />
                  <img :src="buttonImgSrc" />
                </button>
              </div>
            </li>
          </ul>
          <ul>
            <li>
              <p><img src="@/assets/img/txt/04_event_sns_txt_03.png" /></p>
            </li>
            <li>
              <input
                ref="inputEl"
                type="hidden"
                value="#영풍문고 #그랜드오픈 #리뉴얼 #랜선집들이 @ypbooks"
                @focus="$event.target.select()"
              />
              <button type="button" @click="handleCopy" class="sns_copy">
                <img src="@/assets/img/btn/btn_2.png" />
              </button>
            </li>
          </ul>
          <ul>
            <li>
              <p><img src="@/assets/img/txt/04_event_sns_txt_04.png" /></p>
            </li>
          </ul>
        </div>
      </div>
      <div class="sns_submit flex">
        <input
          type="text"
          placeholder="공유한 SNS 게시물 주소를 입력해 주세요."
          onfocus="this.placeholder = ''"
        />
        <button><img src="@/assets/img/btn/btn_3.png" /></button>
      </div>
      <div :class="{ caution_box: true, active: isOpen }">
        <div class="caution">
          <div class="caution_title flex">
            <p :class="{ 'is-open': isOpen }">
              <img src="@/assets/img/ico_info.png" /> 유의사항
            </p>
            <button
              type="button"
              :class="[
                'btn btn--primary btn--viewing-status',
                { 'is-open': isOpen },
              ]"
              @click="toggleCaution"
            >
              <i class="ic ic--dropdown"></i>
            </button>
          </div>
          <ul class="caution_txt" v-if="isOpen">
            <li>당첨자 발표 : 2024년 7월 24일 (수)</li>
            <li>적립금 사용기간 : 지급일로부터 30일 이내</li>
            <li>중복 참여할 수 있지만, 적립금은 ID당 1회 지급됩니다.</li>
            <li>
              비정상적이거나 불법적인 방법으로 이벤트에 참여한 경우,
              <br /><span
                >당첨자 선정 대상에서 제외될 수 있으며 당첨 후에도 취소될 수
                있습니다.</span
              >
            </li>
            <li>
              본 이벤트는 당사의 사정에 따라 별도 고지 없이 변경 또는 종료 될 수
              있습니다.
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { ref } from 'vue';
import Roulette from './detail/Roulette.vue';

export default {
  components: {
    Roulette,
  },
  setup() {
    const inputEl = ref(null);
    const handleCopyForIE = () => {
      inputEl.value.setAttribute('type', 'text');
      inputEl.value.select();
      document.execCommand('copy');
    };

    const handleCopy = () => {
      if (!inputEl.value) {
        return;
      }
      if (!navigator.clipboard) {
        handleCopyForIE();
        return;
      }
      navigator.clipboard
        .writeText(inputEl.value.value)
        .then(() => {
          alert('클립보드에 복사되었습니다');
        })
        .catch(() => {
          handleCopyForIE();
        });
    };
    return {
      inputEl,
      handleCopy,
    };
  },
  data() {
    return {
      isOpen: true,
      showModal: false,
      popupImgSrc: require('@/assets/img/popUpImg.jpg'), // 팝업 이미지 경로
      popupWidth: 500, // 팝업 창 너비
      popupHeight: 500, // 팝업 창 높이
      popupTop: (window.innerHeight - 500) / 2, // 팝업 창 위치 (화면 세로 중앙)
      popupLeft: (window.innerWidth - 500) / 2, // 팝업 창 위치 (화면 가로 중앙)
    };
  },
  methods: {
    toggleCaution() {
      this.isOpen = !this.isOpen; // Toggle isOpen when the button is clicked
    },
    openPopup() {
      const imageUrl = '@/assets/img/popUpImg.jpg';
      window.open(imageUrl, 'ImagePopup', 'width=600,height=400');
    },
    openPopup() {
      const popupWindow = window.open(
        '',
        '_blank',
        `width=${this.popupWidth}, height=${this.popupHeight}, top=${this.popupTop}, left=${this.popupLeft}`
      );
      const content = `
        <html>
          <head>
            <title>Popup Image</title>
          </head>
          <body style="margin: 0; text-align: center;">
            <img src="${this.popupImgSrc}" alt="Popup Image" />
          </body>
        </html>`;
      popupWindow.document.write(content);
      popupWindow.document.close();
    },
  },
};
</script>
<style scoped>
.tablist {
  width: 100%;
  min-height: 110px;
  background: url('@/assets/img/tab/bg.jpg') no-repeat center/contain;
}

.sec_1 {
  width: 100%;
  background: url('@/assets/img/bg/02_roulett_bg.jpg') no-repeat center/cover;
  position: relative;
  padding: 5rem 0;
}

.sec_2 {
  width: 100%;
  background: url('@/assets/img/bg/03_event_coupon_bg.jpg') no-repeat
    center/cover;
  position: relative;
  padding: 0 0 5rem;
}

.sec_3 {
  width: 100%;
  background: url('@/assets/img/bg/04_event_sns_bg.jpg') no-repeat center/cover;
  position: relative;
  padding: 0 0 5rem;
  image-rendering: pixelated;
}

.caution_box {
  width: 75%;
  height: 200px;
  /* border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 20px;
  padding: 1.5rem 2rem; */
  margin: 0 auto;
}

.caution {
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 20px;
  padding: 1rem 1.5rem;
}

.caution_title {
  width: 100%;
  justify-content: space-between;
}

.caution_title img {
  vertical-align: bottom;
  margin-right: 5px;
}

.caution_title p {
  font-weight: 700;
  font-size: 1.125rem;
  color: #4c4c4a;
}

.caution_title button.is-open i {
  transform: rotate(180deg);
}

.caution_txt {
  width: 100%;
  margin-top: 1rem;
  padding-top: 1rem;
  border-top: 1px solid rgba(0, 0, 0, 0.1);
}

.caution_txt {
  list-style: inside;
}

.caution_txt li {
  line-height: 1.8;
  color: #757374;
  font-size: 0.9rem;
  letter-spacing: -0.5px;
}

.caution_txt li::marker {
  font-size: 0.5rem;
  line-height: 1.8;
}

.caution_txt li span {
  display: inline-block;
  text-indent: 10px;
}

.sns_caution,
.sns_submit {
  width: 640px;
  align-items: flex-start;
  justify-content: space-between;
}

.sns_caution_info {
  align-items: flex-start;
}

.sns_caution_info ul:nth-of-type(2) {
  border-top: 1px solid;
  border-bottom: 1px solid;
  padding: 40px 0;
  margin: 40px 0;
}

.sns_caution_info ul li button {
  display: inline-block;
  margin: 25px 0 0 80px;
}

.sns_submit {
  margin: 80px 0;
}

.sns_submit input {
  max-width: 455px;
  width: 100%;
  height: 70px;
  border-radius: 6px;
  border-width: 1px;
  font-size: 1.25rem;
  text-indent: 20px;
}

.sns_submit input:focus {
  outline: none;
}

.modal {
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgb(0, 0, 0);
  background-color: rgba(0, 0, 0, 0.9);
}

.modal-content {
  margin: 15% auto;
  padding: 20px;
  width: 80%;
  max-width: 600px;
  background-color: #fefefe;
  border: 1px solid #888;
  border-radius: 5px;
  position: relative;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
