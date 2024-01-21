<template>
  <div>
    <input v-model="userInput" type="text" placeholder="코드를 입력하세요">
    <button @click="checkCode">확인</button>

    <!-- 입력값이 1010이면 이미지를 보여줌 -->
    <img v-if="isCodeCorrect" src="../assets/seon.png" alt="원하는 이미지" style="height: 70%; width:70%">
  </div>
</template>

<script>
export default {
  data() {
    return {
      userInput: '',
      isCodeCorrect: false
    };
  },
  methods: {
    checkCode() {
      // 입력값이 1004이면 isCodeCorrect를 true로 설정
      this.isCodeCorrect = this.userInput === '1004';

      // 입력값이 1004가 아니면 알람창에 "no"를 띄움
      if (!this.isCodeCorrect) {
        window.alert('바봉!');
      }
    }
  }
};
</script>