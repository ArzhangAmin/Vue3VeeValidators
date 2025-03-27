<template>
  <div class="card-front">
    <div class="center-wrap">
      <Form
        @submit="login"
        class="section text-center"
        :validation-schema="loginFormSchema"
      >
        <h4 class="mb-4 pb-3">Login</h4>
        <div class="form-group">
            <Field
            type="text"
            class="form-style"
            placeholder="Enter your email"
            autocomplete="off"
            name="email"
            :validateOnInput="true"
          />
          <i class="input-icon uil uil-at"></i>
        </div>
        <p class="text-danger">
          <ErrorMessage name="email" />
        </p>
        <div class="form-group mt-2">
          <Field
            type="password"
            class="form-style"
            placeholder="Enter your password"
            autocomplete="off"
            name="password"
            :validateOnInput="true"
          />
          <i class="input-icon uil uil-lock-alt"></i>
        </div>
        <p class="text-danger">
          <ErrorMessage name="password" />
        </p>
        <button class="btn mt-4">Login</button>
        <p class="mb-0 mt-4 text-center">
          <a href="#0" class="link">Forgot your password?</a>
        </p>
      </Form>
    </div>
  </div>
</template>

<script>
import { Form, Field, ErrorMessage } from "vee-validate";
import { object, string } from "yup";
export default {
  name: "LoginForm",
  components: { Form, Field, ErrorMessage },
  data() {
    const loginFormSchema = object({
      email: string().required("Please enter your email").email("Invalid email"),
      password: string()
        .required("Please enter your password")
        .min(6, "Password must be more than 5 characters"),
    });
    return {
      loginFormSchema,
    };
  },
  methods: {
    login(values) {
      console.log(values);
    },
  },
};
</script>

<style></style>