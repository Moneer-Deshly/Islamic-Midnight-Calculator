<script>
import Router from "svelte-spa-router";

import Home from "./routes/Home.svelte";
import About from "./routes/About.svelte";

let routes = {
  "/": Home,
  "/about": About
}
</script>

<main>
  <header>
    <h1 class="home"><a href="/#/">Islamic Midnight Calculator</a></h1>
    <h1 class="about"><a href="/#/about">About</a></h1>
  </header>
  <div>
    <Router {routes}/>
  </div>
</main>

<style>
header {
    display: flex;
    justify-content: space-between;
    align-items: center; 
    padding: 2rem; 
}

.home{
  padding-left: 3rem;
}

.about{
  padding-right: 6rem;
}
</style>
