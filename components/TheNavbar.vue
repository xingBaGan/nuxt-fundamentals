<template>
  <nav class="nav">
    <div class="log">
      <nuxt-link :to="{name:'index'}" class="logo text-lg">Nuxt Fundametals</nuxt-link>
      <span class="subheader">A Vue School course</span>
    </div>
  </nav>
</template>
<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 4.5em;
  font-weight: lighter;
  letter-spacing: 0.5px;
}
.nav .log {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.nav .logo .subheader {
  opacity: 0.7;
  font-size: 0.9rem;
  color: white;
}
.nav .nav-content {
  font-size: 1rem;
}
.nav-content ul {
  display: flex;
  list-style: none;
}
.nav-content ul li {
  padding: 2px 10px;
}
.nav-content ul li:not(:first-of-type) {
  border-left: 1px solid rgb(255, 255, 255, 0.2);
}
</style>
