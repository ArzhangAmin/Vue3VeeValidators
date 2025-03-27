<template>
  <a href="https://codeyad.com/c/33d" class="logo" target="_blank">
    <img src="https://codeyad.com/assets/images/logo.png" alt="" />
  </a>
  <div class="section">
    <div class="container">
      <div class="row full-height justify-content-center">
        <div class="col-12 text-center align-self-center py-5">
          <div class="section pb-5 pt-5 pt-sm-2 text-center">
            <h6 class="mb-0 pb-3">
              <span>Sign Up</span>
              <span>Sign In</span>
            </h6>
            <input
              class="checkbox"
              type="checkbox"
              id="reg-log"
              name="reg-log"
            />
            <label for="reg-log"></label>
            <div class="card-3d-wrap mx-auto">
              <div class="card-3d-wrapper">
                <login-form></login-form>
                <register-form></register-form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LoginForm from "./components/LoginForm.vue";
import RegisterForm from "./components/RegisterForm.vue";
export default {
  name: "App",
  components: { LoginForm, RegisterForm },
};
</script>

<style></style>
