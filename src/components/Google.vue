<template lang="html">
  <div>
    <div class="chat-input" v-if="signedIn">
    <img :src="user.photoURL" class="col-md-1 img-responsive">
    <button class="btn btn-danger" @click="signOut">Sign Out</button>
  </div>
 <div class="chat-login" v-else>
   <button class="loginBtn loginBtn--google" @click="signInWithGoogle">Sign In With Google</button>
 </div>

  </div>
</template>

<script>
export default {
  name: 'Google',
  data() {
    return {

    }
  },
  methods: {
    signInWithGoogle() {
      firebase.auth().signInWithPopup(new firebase.auth.GoogleAuthProvider)
      .then(user => {
        console.log('user',user)
      })
      .catch(error => {
        console.log('error',error)
      })
    }
  },
  mounted() {

  }
}
</script>

<style scoped lang="css">
.loginBtn {
box-sizing: border-box;
position: relative;
/* width: 13em;  - apply for fixed size */
margin: 0.2em;
padding: 0 15px 0 46px;
border: none;
text-align: left;
line-height: 34px;
white-space: nowrap;
border-radius: 0.2em;
font-size: 16px;
color: #FFF;
margin-bottom: 10px;
}
.loginBtn:before {
content: "";
box-sizing: border-box;
position: absolute;
top: 0;
left: 0;
width: 34px;
height: 100%;
}
.loginBtn:focus {
outline: none;
}
.loginBtn:active {
box-shadow: inset 0 0 0 32px rgba(0,0,0,0.1);
}

.loginBtn--google {
  background: #DD4B39;
}
.loginBtn--google:before {
  border-right: #BB3F30 1px solid;
  background: url('https://s3-us-west-2.amazonaws.com/s.cdpn.io/14082/icon_google.png') 6px 6px no-repeat;
}
.loginBtn--google:hover,
.loginBtn--google:focus {
  background: #E74B37;
}
</style>
