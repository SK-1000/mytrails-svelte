<script>
  import {setContext} from "svelte";
  import Main from "./pages/Main.svelte"
  import Login from "./pages/login-view.svelte"
  import Signup from "./pages/signup-view.svelte"
  import {MytrailsService} from "./services/MytrailsService";
  import Dashboard from "./pages/dashboard-view.svelte"

  import Router from "svelte-spa-router";

  setContext("MytrailsService", new MytrailsService("http://localhost:4000"));

  let routes = {
    "/": Main,
    "/login": Login,
    "/signup": Signup,
    "/main": Main,
    "/dashboard": Dashboard,
    "/logout": Main
  }
</script>

<div class="container">
  <Router {routes}/>
</div>