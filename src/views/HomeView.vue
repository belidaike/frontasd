<template>
 
    <h1 class="text-center">Home</h1>
  
    
  <div class="row d-flex justify-content-center ">
    <div class="col-md-2">
      <div class="card" >
    <div class="card-body bg-secondary">
      <h5 class="card-title text-center">User Information</h5>
      <p class="card-text text-center">
        Lastname: {{ user.lname }}
        <br />
        Firstname: {{ user.fname }}
        <br />
        Mobile: {{ user.mobile }}
        <br />

        Course: {{ user.course }}
        <br />
        Year: {{ user.year }}
        <br />
      </p>
      <div class="col-md=12 text-center">
        <a href="#" class="btn btn-danger text-center">
        Go Somewhere
      </a>
      </div>
    </div>
  </div>
    </div>
  </div>
</template>

<script>
import { useAuthStore } from "../stores/auth";
import { useRouter } from "vue-router";

export default {
  setup() {
    const { user, token } = useAuthStore();
    const router = useRouter();

    if (token == "") {
      router.replace("/login");
    }

    return {
      user,
      token,
    };
  },
};
</script>

<style></style>
