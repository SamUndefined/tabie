<template>
    <button class="scroll">
        ↑ 
    </button>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.scroll {
    border-radius: 100%;
    background-color: rgba(0, 0, 0, 0.9);
    color: whitesmoke;
    /* display: none; */
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
