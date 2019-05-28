<template>
  <button id="toTopButton" :class="'scroll ' + displayClass" @click="toTop">
    ↑ 
  </button>
</template>

<script>

export default {
  name: "ScrollToTop",
  props: ['afterDistance'],
  data() {
    return {
      displayClass: ''
    }
  },
  mounted() {
    window.onscroll = () => {
      const 
        button = document.getElementById("toTopButton"),
        distance = this.$props.afterDistance ? this.$props.afterDistance : 500,
        shouldDisplayButton = document.body.scrollTop > distance || document.documentElement.scrollTop > distance

      this.displayClass = shouldDisplayButton ? 'slide-in' : 'hide'
    }
  },
  destroyed() {
    window.onscroll = undefined;
  },
  methods: {
    toTop () {
        document.body.scrollTop = 0; // For Safari
        document.documentElement.scrollTop = 0; // For Chrome, Firefox, IE and Opera
    }
  }
}
</script>

<style lang="scss">
.scroll {
  border-radius: 100%;
  background-color: rgba(0, 0, 0, 0.9);
  color: whitesmoke;
  display: none;
  position: fixed;
  bottom: 0px;
  right: 30px;
  z-index: 99;
  border: 1px solid currentColor;
  outline: none;
  cursor: pointer;
  padding: 10px 15px;
  font-size: 1.25rem;
  animation: animatebottom 0.4s;

  &:hover {
    transform: scale(1.10, 1.10);
  }
}

.hide {
  display: none;
}

.slide-in {
  display: block;
  transform: translateY(50px);
  animation: slide-in 0.5s ease forwards;
}

@keyframes slide-in {
  to { transform: translateY(-20px); }
}
</style>
