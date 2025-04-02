<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{name : 'custList'}">전체조회</router-link> |
    <!-- <router-link :to="{name : 'custInfo'}">단건조회</router-link> | -->
    <router-link :to="{name : 'custAdd'}">추가</router-link> |
    <!-- <router-link :to="{name : 'custUpdate'}">수정</router-link> -->
  </nav>
  <router-view/>
</template>