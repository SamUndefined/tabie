<template>
  <menu>
    <ul class="menu">
      <g-link to="/about" tag="li"><a>About</a></g-link>
      <g-link to="/contact" tag="li"><a>Contact</a></g-link>
    </ul>
  </menu>
</template>

<style>
.menu {
  margin: -1rem auto 2rem;
  width: 50%;
  list-style-type: none;
  text-align: center;
}

.menu li {
  display: inline-block;
  margin: auto 2rem;
}

.menu li a {
  text-decoration: none;
}
</style>
