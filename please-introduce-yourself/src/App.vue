<template>
  <div id="app" class="jumbotron">
    <div class="container">
      <h1>Hello!  Nice to meet you!</h1>
      <div v-for="message in messages" :key="message.id">
        <h4>{{ message.title}}</h4>
        <p>{{ message.text }}</p>
        <p>{{ message.timestamp }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import Firebase from 'firebase'
var config = {
  apiKey: 'AIzaSyBThlzNI-L4dky9SnUhy1LC_MzcVgzOqiU',
  authDomain: 'pleaseintroduceyourself-f2906.firebaseapp.com',
  databaseURL: 'https://pleaseintroduceyourself-f2906.firebaseio.com',
  projectId: 'pleaseintroduceyourself-f2906',
  storageBucket: 'pleaseintroduceyourself-f2906.appspot.com',
  messagingSenderId: '474567875924'
}
let app = Firebase.initializeApp(config)

let db = app.database()
let messagesRef = db.ref('messages')

export default {
  name: 'App',
  firebase: {
    messages: messagesRef
  }
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
