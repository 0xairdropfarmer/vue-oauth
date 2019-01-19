<template>
  <div class="container">
    <h1>Social Login with OAuth.io</h1>
    <div class="row">
      <div class="col-sm-4 social-buttons"><hr /></div>
      <div class="col-md-4 col-md-offset-3 social-buttons">
        <OAuth api_key="Fcdn9FAU7dhM0TzQ7umztVA28NM" provider="facebook" />
        <OAuth api_key="Fcdn9FAU7dhM0TzQ7umztVA28NM" provider="github" />
      </div>
    </div>
  </div>
</template>

<script>
import OAuth from "./components/OAuth";

export default {
  name: "App",
  components: {
    OAuth
  }
};
</script>
