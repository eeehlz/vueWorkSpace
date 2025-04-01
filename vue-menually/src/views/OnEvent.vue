<!--views/OnEvent.vue-->
<template>
  <div>
    <input v-model="msg"
           v-on:keyup.alt.enter="clear();">
    <p>{{ msg }}</p>
    <hr>
    <form v-on:click.self="message('form')">  <!-- self : 나를 선택 할때만 작동-->
      Form
      <div v-on:click.once="message('div')"> <!--once : 한번 실행되면 끝-->
        Div
        <p @click.stop="message('p')"> <!--stop : 부모로 못하게 막는다. 버블링 방지 최고 레벨-->
          P
          <a @click.prevent="message('a')"
            href="http://www.github.com">깃허브</a>
        </p>
      </div>
    </form>
    <button @click="increaseCounter">Add 1</button>
    <br>
    <button @click="setCount(num, $event)">Add {{ num }}</button>
    <p>The Counter is : {{ counter }}</p>
  </div>
</template>
<script>
export default {
  data(){  //데이터(CRUD) => 프로퍼티
    return {
      msg : '',
      num : 7,
      counter : 0,
    }
  },
  methods : {
    clear(){
      this.msg = '';
    },
    message(tag){
      alert(`${tag}, 선택`)
    },
    increaseCounter(event){
      console.log('increase',event);
      this.counter++;
    },
    setCount(value, event){
      console.log('setCount', event);
      this.counter += value;
    }
  }
}
</script>
<style>
form, form * {
  margin: 10px;
  border: 1px solid black;
}
</style>