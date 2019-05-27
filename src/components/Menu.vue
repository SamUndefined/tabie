<template>
  <menu>
    <ul class="menu">
      <g-link v-for="edge in $static.menuPages.edges" :key="edge.node.id" :to="edge.node.path" tag="li">
        <a>{{edge.node.title}}</a>
      </g-link>
    </ul>
  </menu>
</template>

<static-query>
query MenuPages {
  menuPages: allMenuPage {
    edges {
      node {
        id
        title
        path
      }
    }
  }
}
</static-query>

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
