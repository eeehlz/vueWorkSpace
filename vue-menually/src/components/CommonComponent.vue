<!-- components/CommonComponent.vue -->
<template>
  <!-- Component가 가지는 HTML 태그 를 template 태그 가 가짐 -->
  <p>{{ year }}년 {{ month }}월 {{ day }}</p>
  <p>다음해 {{ afterYear }}</p>
</template>

<script>
  // Component를 관리하는 Vue 객체 정의 : DATA 포함
  export default {
    data() { // 데이터 (CRUD) => 프로퍼티
      let today = new Date();
      return {
        year: today.getFullYear(),
        month: today.getMonth() + 1,
        day: today.getDate(),
      }
    },

    computed: { //기존 데이터를 기반으로 연산한 결과값(Read Only)
      // => 프로퍼티
      afterYear() { // afterYear(){} == afterYear : function(){} : 객체 아님 함수
        return this.year + 1;
      },
    },
    methods: {}, // Vue가 사용하는 모든 종류의 함수

    watch: { // 데이터 변경에 따른 추가 작업 정의 - 감시자
      month() {
        console.log('실행', this.month);
        if((this.month.toString()).length == 1 && this.month < 10) {
          this.month = '0' + this.month;
        }
      }
    }
  }
</script>

<style scoped>
  /* Component가 가지는 Style */
</style>