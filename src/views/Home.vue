
<template>
  <div class="home">
    <div class="content">
      <div class="one">
        <textarea v-model="input"></textarea>
      </div>
      <div class="two"></div>
    </div>
    <!--<img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
  </div>
</template>

<script>
// @ is an alias to /src
// eslint-disable-next-line
//import HelloWorld from "@/components/HelloWorld.vue";

export default {
  // eslint-disable-next-line
  name: "home",
  components: {
    // eslint-disable-next-line
    //HelloWorld
    // eslint-disable-next-line
  },
  data() {
    return {
      input: ""
    };
  }
};
</script>
<style scoped lang='scss'>
@import "../../public/styles.scss";

.content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 2px;
}
.one,
.two {
  border: 5px solid orangered;
  height: 600px;
}
textarea {
  width: 100%;
  height: 100%;
}
</style>
