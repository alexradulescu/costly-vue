<template>
  <div class="hello">
    <h1></h1>
    <form @submit="addExpense">
      <input type="text" v-model="newExpense.title" placeholder="Title" required />
      <input type="number" v-model="newExpense.value" placeholder="Value" required />
      <button type="submit">Save</button>
    </form>
    <ul>
      <li v-for="cost in costs">
        {{cost.title}} - {{cost.value}}
      </li>
    </ul>
    <!-- <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul> -->
  </div>
</template>

<script>
import Firebase from 'firebase';

let config = {
  apiKey            : 'AIzaSyAOZ3OY01SP_jkHasKe3iFwGCL2b8MHd0A',
  authDomain        : 'costly-7a6ba.firebaseapp.com',
  databaseURL       : 'https://costly-7a6ba.firebaseio.com',
  projectId         : 'costly-7a6ba',
  storageBucket     : 'costly-7a6ba.appspot.com',
  messagingSenderId : '935666435863'
};

let app       = Firebase.initializeApp(config)
let db        = app.database()
let costList  = db.ref('costList')

export default {
  name: 'HelloWorld',
  data () {
    return {
      newExpense: {
        title: '',
        value: null
      }
    }
  },
  firebase: {
    costs: costList
  },
  methods: {
    addExpense(e) {
      e.preventDefault();
      costList.push(this.newExpense);
      this.newExpense.title = '';
      this.newExpense.value = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
