<script setup lang="ts">
import KakaoMap from "./atom/KakaoMap.vue";
import LocationButton from "./atom/LocationButton.vue";
import LocationText from "./atom/LocationText.vue";
import TextCopy from "./atom/TextCopy.vue";
const props = defineProps({
  type: String,
});
</script>

<template>
  <KakaoMap />
  <TextCopy
    :class="['location_copy', type]"
    copy-text="서울특별시 서초구 반포대로 235"
  >
    <slot>
      <p><em>라도무스 아트센터</em></p>
      <p>대전광역시 유성구 동서대로 639</p>
    </slot>
  </TextCopy>
  <div :class="['btn_locations', type]">
    <LocationButton type="naver" link="https://naver.me/xM2E86s2"
      ><span class="text">네이버지도</span></LocationButton
    >
    <LocationButton type="kakao" link="http://kko.to/hdV-T0HnHP"
      ><span class="text">카카오맵</span></LocationButton
    >
    <LocationButton type="tmap" link="https://surl.tmobiapi.com/bb86b4c4"
      ><span class="text">티맵</span></LocationButton
    >
  </div>
  <div :class="['text_locations', type]">
    <LocationText title="자가용 이용시">
      <p class="text">
        서대전IC, 유성IC에서 10분거리로 1300대 동시주차 가능합니다.
      </p>
      <p class="text">주차시간의 제한이 없습니다.</p>
    </LocationText>
    <LocationText title="KTX 기차 이용시">
      <p class="text">
        대전역 1호선(반석행) > 유성온천 6번 출구 > 706버스 > 아이파크시티 하차 >
        도보 5분 소요
      </p>
    </LocationText>
    <LocationText title="시외 고속버스 이용시">
      <p class="text">
        유성 시외 버스터미널 > 312버스 > 홍도 초등학교 하차 > 도보 10분 소요
      </p>
    </LocationText>
  </div>
</template>

<style>
.btn_locations {
  display: flex;
  gap: 1px;
  margin: 0 auto;
}
.text_locations {
  margin-top: 1rem;
}

.location_copy,
.text_locations .text {
  font-family: "Nanum Myeongjo", serif;
  font-size: 16px;
  padding: 20px 0;
}

.location_copy em {
  font-style: normal;
  font-weight: bold;
}

.btn_locations .text {
  font-size: 13px;
}

.location_copy.default,
.btn_locations.default .text,
.text_locations.default .text {
  font-family: "Nanum Myeongjo", serif;
  font-size: 13px;
}
</style>
