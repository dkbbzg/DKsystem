<template>
  <div class="login-page">
    <div class="box">
      <p>Welcome</p>
      <p class="tips">Please enter your account number and password to log in.</p>
      <div><input type="text" placeholder="Account Number"></div>
      <div><input type="password" placeholder="Password"></div>
      <div class="button-login">Login</div>
      <div class="link">
        <div class="pwd">Password</div>
        <span>|</span>
        <div class="register">Register</div>
      </div>
    </div>
  </div>
</template>

<script>
import store from '../vuex/store.js'
export default {
  name: 'Login',
  store
}
</script>

<style scoped>
.login-page {
  background-color: rgba(0, 0, 0, .7);
}
.login-page::before {
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  background: url('../../static/img/login_bg.jpeg') no-repeat bottom center;
  z-index: -1;
}

.box {
  display: flex;
  width: 100%;
  height: 100%;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.box > p {
  font-size: 70px;
  color: #fff;
  letter-spacing: 1.6px;
}
.box > p.tips {
  font-size: 24px;
  line-height: 30px;
  letter-spacing: 1px;
  width: 450px;
  text-align: center;
  margin-top: 10px;
}
.box > div {
  margin-top: 20px;
}
.box > div > input,
.box > div.button-login {
  font-size: 16px;
  height: 50px;
  line-height: 50px;
  background: #003d75;
  width: 370px;
  text-align: center;
  border-radius: 25px;
  color: #fff;
  letter-spacing: 1px;
  cursor: pointer;
}
.box > div > input {
  border: 1px solid #fff;
  background: transparent;
}
.box > div.link {
  color: #fff;
  width: 370px;
  padding: 0 40px;
  text-align: center;
  display: flex;
  justify-content: space-around;
}
</style>
