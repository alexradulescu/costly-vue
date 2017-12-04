<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
  </div>
</template>

<script>
// import Firebase from 'firebase';

// let config = {
//   apiKey            : 'AIzaSyAOZ3OY01SP_jkHasKe3iFwGCL2b8MHd0A',
//   authDomain        : 'costly-7a6ba.firebaseapp.com',
//   databaseURL       : 'https://costly-7a6ba.firebaseio.com',
//   projectId         : 'costly-7a6ba',
//   storageBucket     : 'costly-7a6ba.appspot.com',
//   messagingSenderId : '935666435863'
// };

// let app       = Firebase.initializeApp(config)
// let db        = app.database()
// let costList  = db.ref('costList')

export default {
  name: 'app',
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
