<template>
  <div class="card-back">
    <div class="center-wrap pt-5 pb-5">
      <Form
        @submit="register"
        :validation-schema="registerFormSchema"
        :initialValues="formData"
        class="section text-center"
      >
        <h4 class="mb-4 pb-3">Register</h4>
        <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <Field
                type="text"
                class="form-style"
                placeholder="Full Name"
                autocomplete="off"
                name="name"
              />
              <i class="input-icon uil uil-user"></i>
            </div>
            <p class="text-danger">
              <ErrorMessage name="name" />
            </p>
          </div>
          <div class="col-md-6">
            <div class="form-group">
              <Field
                type="email"
                class="form-style"
                placeholder="Enter your email"
                autocomplete="off"
                name="email"
              />
              <i class="input-icon uil uil-at"></i>
            </div>
            <p class="text-danger">
              <ErrorMessage name="email" />
            </p>
          </div>

          <div class="col-md-6">
            <div class="form-group mt-2">
              <Field
                type="password"
                class="form-style"
                placeholder="Password"
                autocomplete="off"
                name="password"
                :validateOnInput="true"
              />
              <i class="input-icon uil uil-lock-alt"></i>
            </div>
            <p class="text-danger">
              <ErrorMessage name="password" />
            </p>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-2">
              <Field
                type="password"
                class="form-style"
                placeholder="Confirm Password"
                autocomplete="off"
                name="confirmPassword"
                :validateOnInput="true"
              />
              <i class="input-icon uil uil-lock-alt"></i>
            </div>
            <p class="text-danger">
              <ErrorMessage name="confirmPassword" />
            </p>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-2">
              <Field
                type="text"
                class="form-style"
                placeholder="Phone Number"
                name="phoneNumber"
                autocomplete="off"
                :validateOnInput="true"
              />
              <i class="input-icon uil uil-phone"></i>
            </div>
            <p class="text-danger">
              <ErrorMessage name="phoneNumber" />
            </p>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-2">
              <Field as="select" name="role" class="form-style">
                <option value="">Select your role</option>
                <option value="user">User</option>
                <option value="student">Student</option>
                <option value="teacher">Teacher</option>
              </Field>
              <i class="input-icon uil uil-rupee-sign"></i>
            </div>
            <p class="text-danger">
              <ErrorMessage name="role" />
            </p>
          </div>
          <div class="col-md-6">
            <div class="form-group mt-3" style="text-align: left">
              <label for="1">Unspecified</label>
              <Field
                type="radio"
                id="1"
                class="m-2"
                value="Unspecified"
                name="gender"
              />

              <label for="2">Female</label>
              <Field
                type="radio"
                id="2"
                class="m-2"
                value="Female"
                name="gender"
              />
              <label for="3">Male</label>
              <Field
                type="radio"
                id="3"
                class="m-2"
                value="Male"
                name="gender"
              />
            </div>
          </div>
        </div>
        <button class="btn mt-4">Register</button>
      </Form>
    </div>
  </div>
</template>

<script>
import { Form, Field, ErrorMessage } from "vee-validate";
import { object, string, ref } from "yup";

export default {
  data() {
    const registerFormSchema = object({
      name: string().required("Please enter your name"),
      email: string().required("Please enter your email").email("Invalid email"),
      phoneNumber: string()
        .required("Please enter your phone number")
        .min(11, "Invalid phone number")
        .max(11, "Invalid phone number"),
      password: string()
        .required("Please enter your password")
        .min(6, "Password must be more than 5 characters"),
      confirmPassword: string()
        .required("Please confirm your password")
        .oneOf([ref("password"), null], "Passwords do not match"),
      role: string().required("Please select your role"),
    });
    return {
      registerFormSchema,
      formData: {
        gender: "Male",
        role: "user",
      },
    };
  },
  components: {
    Form,
    Field,
    ErrorMessage,
  },
  methods: {
    register(values) {
      console.log(values);
    },
  },
};
</script>

<style></style>