
<script>
import Banner from "/src/assets/banner.png";
import WelcomeMenu from "C:/Users/User/OneDrive/Documents/Full Stack Web Dev/assignment 1/mytrails-svelte/src/components/welcome-menu.svelte";
import {push} from "svelte-spa-router";

  let email = ""
  let password = "";

  async function login() {
    push("/dashboard");
  }
</script>


<WelcomeMenu/>
<!-- {{> welcome-menu active="login"}} -->

<section class="section">
  <h1 class="title">Log in</h1>
  <form on:submit|preventDefault={login}>
    <!-- <form action="/authenticate" method="POST"> -->
    <div class="field">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label class="label">Email</label> 
      <!-- <input class="input" type="text" placeholder="Enter email" name="email"> -->
      <input bind:value={email} class="input" id="email" name="email"placeholder="Enter email" type="text">
    </div>
    <div class="field">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <label class="label">Password</label> 
      <!-- <input class="input" type="password" placeholder="Enter Password" name="password"> -->
      <input bind:value={password} class="input" id="password" name="password" placeholder="Enter Password" type="password">
    </div>
    <div class="field is-grouped">
      <button class="button is-link">Submit</button>
    </div>
  </form>
</section>
  <figure class="image is-2by1">
      <!-- <img src="/images/banner.png"> -->
      <img src={Banner}  alt="hiker on a mountain">
    </figure>