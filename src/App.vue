<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/mountain-logo.png">
        <h1> Summit Fitness </h1>
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/browse.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/shopcart.png">
          <p>{{cartLength}} items</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class="h-divider"></div>
  <div class="footer">
    <p>Find Kinsley on <a href="https://github.com/kinsleyc/creative-project-3" target="_blank">Github</a></p>
    <p>Find Ty on <a href="https://github.com/kinsleyc/creative-project-3" target="_blank">Github</a></p>
  </div>
</div>
</template>

<script>
export default {
  computed: {
    cartLength() {
      let length = this.$root.$data.cart.length;
      return length;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;
  background-color: #000000;

}

#menu a {
  color: white;
  text-decoration: underline;
}

#menu a:hover {
  text-decoration: none;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}


#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
  text-align: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  margin-top: 10px;
  margin-right: 10px;
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

.h-divider {
    height: 1px;
    width: 100%;
    border-top: 1px solid white;
}

.footer {
    color: white;
    display: flex;
    margin-top: 20px;
    margin-bottom: 20px;
    flex-direction: column;
    align-items: center;
}

.footer a {
    color: white;
    text-decoration: underline;
}

.footer a:hover {
    text-decoration: none;
}
</style>
