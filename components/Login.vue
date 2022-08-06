<template>
	<div class="login">
    <div class="col-md-3 mx-auto py-5 px-3">
      <h3 class="text-white">Login</h3>
      <input type="email" v-model="email" id="email" class="form-control my-3" placeholder="Email">
      <input type="password" v-model="password" id="inputPassword" class="form-control my-3" placeholder="Password">
      <div class="form-check">
        <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
        <label class="form-check-label text-white" for="flexCheckDefault">
          Remember me
        </label>
        <a class="float-end text-decoration-none" href="#">Forgot password?</a>
      </div>
      <div v-if="isProgress" class="spinner-border text-primary my-4" role="status">
          <span class="visually-hidden">Loading...</span>
      </div>
      <button v-else v-on:click="login" class="btn w-100 my-4 btn-login text-white fw-bold" type="submit">Sign in</button>
      <div class="text-center">
        <span class="text-white">Need an account? </span><a class="text-decoration-none" href="">Register now</a>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import api from '../api/index';
export default {
name:"Login",
data(){
  return {
    isProgress:false,
    email:'',
    password:''
  }
},
methods:{
login:function(){
  if(this.email.length==0){
    alert("email is not allowed to be empty");
    return;
  }
  if(this.password.length==0){
    alert("password is not allowed to be empty");
    return;
  }
  this.isProgress=true;
  var $this=this;
  axios({
    method: 'post',
    url: api.API_URL+'login',
    data: {
      email:$this.email,
      password:$this.password
    }
  }).then(function (response) {
      if(response.data.error_code=="SUCCESS"){
        $this.$router.push('/successful')
      }else{
        alert(response.data.message)
      }
      $this.isProgress=false;
  }).catch(function (error) {
      alert(error);
      $this.isProgress=false;
  });
}
}
}
</script>

<style>
.login{
  background-color: #0f1735;
}
.btn-login{
  background-color: #9a3192;
  border: none;
}

</style>