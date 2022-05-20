
<script>
import MinimalistHiker from "/src/assets/minimalisthiker.png";
import WelcomeMenu from "C:/Users/User/OneDrive/Documents/Full Stack Web Dev/assignment 1/mytrails-svelte/src/components/welcome-menu.svelte";
import { push } from "svelte-spa-router";
import { getContext } from "svelte";

  let firstName = "";
  let lastName = "";
  let email = ""
  let password = "";
  let errorMessage = "";

  const MytrailsService = getContext("MytrailsService");

  async function signup() {
    let success = await MytrailsService.signup(firstName, lastName, email, password)
    if (success) {
      push("/");
    } else {
      errorMessage = "Error Trying to sign up";
    }
  }
</script>

<WelcomeMenu/>


<!-- {{> welcome-menu active="signup"}} -->
<div class="columns">
  <div class="column is-two-thirds">
<section class="section">
  <h1 class="title">Sign up</h1>
  <!-- <form action="/register" method="POST"> -->
    <form on:submit|preventDefault={signup}>
    <!-- svelte-ignore a11y-label-has-associated-control -->
    <label class="label">Name</label>
    <div class="field is-horizontal">
      <div class="field-body">
        <div class="field">
          <!-- <input class="input" type="text" placeholder="Enter first name" name="firstName"> -->
          <input bind:value={firstName} id="firstname" class="input" type="text" placeholder="Enter first name" name="firstName">
        </div>
        <div class="field">
          <!-- <input class="input" type="text" placeholder="Enter last name" name="lastName"> -->
          <input bind:value={lastName}  id="lastname" class="input" type="text" placeholder="Enter last name" name="lastName">
        </div>
      </div>
    </div>
    <div class="field">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <!-- <label class="label">Email</label> <input class="input" type="text" placeholder="Enter email" name="email"> -->
      <input bind:value={email} id="email" class="input" type="text" placeholder="Enter email" name="email">
    </div>
    <div class="field">
      <!-- svelte-ignore a11y-label-has-associated-control -->
      <!-- <label class="label">Password</label> <input class="input" type="password" placeholder="Enter Password" name="password"> -->
      <input bind:value={password} id="password" class="input" type="password" placeholder="Enter Password" name="password">
    </div>
    <div class="field is-grouped">
      <button class="button is-link">Submit</button>
    </div>
  </form>
  {#if errorMessage}
  <div class="section">
    {errorMessage}
  </div>
{/if}
</section>
  </div>
  <div class="column">
    <figure class="image is-4by5">
      <!-- <img src="/images/minimalisthiker.png"> -->
      <img src={MinimalistHiker}  alt="hiker on a mountain">
    </figure>
  </div>
</div>