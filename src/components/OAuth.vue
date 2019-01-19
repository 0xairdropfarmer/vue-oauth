<template>
  <a @click="Auth();" :class="class2">
    <span :class="class1"></span> Sign in with {{ provider }}
  </a>
</template>
<script>
import { OAuth } from "oauthio-web";
export default {
  props: ["api_key", "provider"],
  data() {
    return {
      class1: "fa fa-" + this.provider,
      class2: "btn btn-block btn-social btn-" + this.provider,
      access_token: ""
    };
  },
  created() {
    OAuth.initialize(this.api_key);
  },
  methods: {
    Auth() {
      OAuth.popup(this.provider)
        .done(res => {
          console.log(res.access_token);
        })
        .fail(err => {
          //todo when the OAuth flow failed
        });
    }
  }
};
</script>
<style>
@import "https://stackpath.bootstrapcdn.com/bootstrap/4.1.2/css/bootstrap.min.css";
@import "https://cdnjs.cloudflare.com/ajax/libs/bootstrap-social/5.1.1/bootstrap-social.min.css";
@import "https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css";
</style>
