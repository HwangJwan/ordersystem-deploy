<template>
<div>hook함수 테스트</div>
<button @click="moveScreen()">다른화면으로 이동(라우트방식)
</button>
<div>{{ count1 }}</div>
<button @click="increseCount1()">count1값 증가</button>
<div>computed된 값: {{ doubleCount }}</div>
</template>

<script>
export default {                                                            
  data() {
    return {
        count1:0,
    };
  },
//   화면이 열리기 전(vue인스턴스가 실행되기 전) 실행되는 함수
//   ex) 목록조회, 상세조회
  created() {
    console.log("created 테스트");
  },
//   컴포넌트가 화면상에서 제거(이동) 될때 실행되는 함수.(물리적 화면을 종료시키는 경우는 제외)
//   ex) 채팅(알림) 화면을 벗어나 다른화면으로 이동시에 실시간 연결 종료요청
  beforeUnmount() {
    console.log("beforeUnmount 테스트");
  },
//   특정 변수의 변경사항을 인지하여 함수를 자동실행하는 hook함수
//   ex) 검색어 입력시, 자동완성 api호출
  watch: {
    // 인지하고자 하는 변수명과 일치되는 함수명 사용
    count1() {
        console.log("count1겂아 변했습니다.");
    },
  },
//   화면 전체의 변경 사항을 인지하는 hook함수
  updated() {
    console.log("updated함수 테스트");
  },
//   종속된 데이터가 변경될때 함수를 실행하여 값을 재계산해서 return하는 함수
  computed: {
//   ex) 장바구니 수량 보여줄때.
    doubleCount() {
        // this.count1이 변하면, doubleCount.함수가 실행되고, doubeCount를 정ㄼㅈ
        return this.count1*2;
    }
  },
  methods: {
    moveScreen() {
        this.$router.push("/practice/conditional");
    },
    increseCount1() {
        this.count1++;
    }
  }
};
</script>

<style></style>
