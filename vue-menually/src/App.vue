<template>
  <nav>
    <router-link to="/">Home</router-link> |    <!--호출 태그-->
    <router-link to="/about">About</router-link> |
    <router-link to="/dataBinding">DataBind</router-link> |
    <router-link :to="{ name : 'listBind'}">ListBind</router-link> |
    <router-link to="/ifBinding">IfBind</router-link> |
    <router-link :to="{ name : 'onEvent'}">onEvent</router-link> |
    <router-link :to="{ name : 'computedWatch'}">computedWatch</router-link> |

  </nav>
  <router-view/>
  <!-- <hr> -->
  <!-- <DataBinding/>   컴포넌트는 독립적이다. 서로 다르게 출력가능  -->
  <!-- <DataBinding/> -->
</template>

<!-- <router-view/> 와 <router-link> 로 동작되기 때문에 밑에 코드는 필요없다.-->
<script>
// 컴포넌트 추가 1) 자식 컴포넌트로 등록
//               2) 특정 페이지의 조각을 구성
// import HomeView from './views/HomeView.vue';
// import About from './views/AboutView.vue'
// import DataBinding from './views/DataBinding.vue';
// import ListBinding from './views/ListBinding.vue';
// import IfBinding from './views/IfBinding.vue';
// import OnEvent from './views/OnEvent.vue';

// export default {
//   components : { // 자식 컴포넌트 정의 <-- Here
//     HomeView,
//     About,
//     DataBinding,
//     ListBinding,
//     IfBinding,
//     OnEvent
//   }
// }
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
