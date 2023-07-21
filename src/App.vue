<template>
  <div class="container p-4">
    <h3>Vue 3 using Vee Validate</h3>
    <Form v-slot="{ errors }">
      <div class="form-group mb-4">
        <label for="email">Email</label>
        <Field name="email" :rules="isRequired" class="form-control" />
        <span class="text-danger">{{ errors.email }}</span>
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <Field name="password" :rules="isRequired" class="form-control" />
        <span class="text-danger">{{ errors.password }}</span>
      </div>
    </Form>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.min.css";
import { Field, Form } from 'vee-validate';
export default {
  name: 'App',
  components: {
    Field,
    Form,
  },
  methods: {
    isRequired(value) {
      return value ? true : 'This field is required';
    },
  },
}
</script>
