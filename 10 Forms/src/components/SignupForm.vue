<template>
  <form>
    <label>Email</label>
    <!--- Using v-model for data binding -->
    <input type="email" required v-model="email" />

    <label>Password</label>
    <input type="password" required v-model="password" />

    <label>Role</label>
    <select v-model="role">
      <option value="developer">Web Developer</option>
      <option value="designer">Web Designer</option>
    </select>
  </form>

  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
</template>

<script>
export default {
  data() {
    // Data function
    return {
      // Returns an object
      email: "",
      password: "",
      role: "",
    };
  },
};
</script>

<style>
label {
  display: inline-block;
}
</style>
