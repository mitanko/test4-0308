<template>
  <div class="profile-accordion">

    <div class="profile-title" @click="toggle">
      <p>アコーディオン</p>
      <div class="base">
        <span class="down-arrow"></span>
      </div>
    </div>

    <transition
      v-on:before-enter="onBeforeEnter"
      v-on:enter="onEnter"
      v-on:bofore-leave="onBeforeLeave"
      v-on:leave="onLeave"
    >

      <div v-show="show" class="accordion-wrapper">
        <div class="accordion-title -ly_contents">
          <p>アコーディオンの中身が入ります</p>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",

  data() {
    return {
      show: false
    };
  },
  methods: {

    toggle: function() {
      this.show = !this.show;
    },


    onBeforeEnter: function(el) {
      el.style.height = 0;
    },
    onEnter: function(el) {
      el.style.height = "130px";
    },
    onBeforeLeave: function(el) {
      el.style.height = "130px";
    },
    onLeave: function(el) {
      el.style.height = 0;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.profile-title {
  display: flex; 
  justify-content: space-between; 
  align-items: center; 
  background: #eee;
  width: 70%;
  height: 70px;
  padding: 0 30px;
  font-size: 20px;
  border: 1px solid #080808; 
}

.accordion-wrapper {
  display: flex; 
  justify-content: space-between; 
  align-items: center; 
  background: rgb(255, 253, 253);
  width: 70%;
  height: 50px;
  padding: 0px 30px;
  font-size: 15px;
  border: 1px solid #080808; 
  border-top-color: whitesmoke;
}

</style>
