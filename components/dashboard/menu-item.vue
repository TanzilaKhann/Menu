<template>
  <div>
    <head>
      <script
        src="https://kit.fontawesome.com/02cb9ab8ae.js"
        crossorigin="anonymous"
      ></script>
    </head>
    <div class="text">
      <i :class="iconType"></i>
      <span :class="max ? ' w1' : ' '" class="" v-show="max">{{
        heading
      }}</span>
    </div>
  </div>
</template>
<style>
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
.hover:hover {
  border-left: 2px solid rgb(240, 235, 235);
}
.text {
  box-sizing: border-box;
  padding: 15px;

  margin-left: 20px;
  font-size: 18px;
}
.text:hover {
  color: rgb(240, 235, 235);
  border-left: 2px solid rgb(240, 235, 235);
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
  },
  methods: {},
};
</script>
