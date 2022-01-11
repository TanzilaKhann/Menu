<template>
  <div>
    <head>
      <script
        src="https://kit.fontawesome.com/02cb9ab8ae.js"
        crossorigin="anonymous"
      ></script>
    </head>
    <div class="margin">
      <div :class="sub ? ' subbg' : ' '" @click="toggle()">
        <i :class="iconType"></i>
        <span :class="max ? ' w1' : ' '" v-show="max">{{ heading }}</span>

        <i class="fas fa-angle-up animation" v-show="icon2" v-if="max"></i>
      </div>
    </div>
    <div v-if="div" v-show="max" class="black">
      <slot></slot>
    </div>
  </div>
</template>
<style>
/* .bg{
    padding: 50px;
} */
@keyframes w1anim {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}
.w1 {
  animation: w1anim 2s;
}
.subbg {
  background-color: #282930;
  padding: 15px;
  margin: -15px -15px -15px -35px;
  /* margin-top:-25px; */
}
.fa-angle-up {
  float: right;
  margin-right: 20px;
}
.margin {
  /* box-sizing: border-box; */
  padding: 15px;
  /* margin-top: 25px; */
  /* margin-bottom: 18px; */
  margin-left: 20px;
  font-size: 18px;
}

.margin:hover {
  cursor: pointer;
  color: rgb(240, 235, 235);
  border-left: 2px solid rgb(240, 235, 235);
}
.black {
  padding: 0px;
  margin-top: 15px;

  margin-left: 0px;
  background-color: #212227;
  text-align: center;
}

i {
  margin: 0px 10px;
}
</style>
<script>
export default {
  data() {
    return {
      icon1: true,
      icon2: false,
      div: false,
    };
  },
  props: {
    heading: {
      type: String,
    },
    iconType: {
      type: String,
    },
    max: {
      type: Boolean,
      default: true,
    },
    sub: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    toggle() {
      this.icon1 = !this.icon1;
      this.icon2 = !this.icon2;
      this.div = !this.div;
    },
  },
};
</script>
