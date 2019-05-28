<template>
    <button id="toTopButton" class="scroll" @click="toTop">
        ↑ 
    </button>
</template>

<script>

export default {
  name: "ScrollToTop",
  props: ['afterDistance'],
  mounted() {
    window.onscroll = () => {
      const 
        buttonStyle = document.getElementById("toTopButton").style,
        distance = this.$props.afterDistance ? this.$props.afterDistance : 500,
        scrolledDownABit = document.body.scrollTop > distance || document.documentElement.scrollTop > distance
      
      scrolledDownABit ? buttonStyle.display = "block" : buttonStyle.display = "none"
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
    bottom: 20px;
    right: 30px;
    z-index: 99;
    border: 1px solid currentColor;
    outline: none;
    cursor: pointer;
    padding: 10px 15px;
    font-size: 1.25rem;

    &:hover {
        transform: scale(1.10, 1.10);
    }
}
</style>
