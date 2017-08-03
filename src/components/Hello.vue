<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-if="!authenticated">
      
      <a @click="auth.login()">Log In</a>

    </div>
    
    <div v-if="authenticated">
    
      <a @click="auth.logout()">Log Out</a>
    
    </div>
    
  <vuetable ref="vuetable" api-url="https://vuetable.ratiw.net/api/users" :fields="['name', 'email', 'birthdate']"></vuetable>


    </ul>
  </div>
</template>

<script>
import Vuetable from 'vuetable-2/src/components/Vuetable'

export default {
  name: 'hello',
  components: { Vuetable },
  props: ['auth', 'authenticated'],
  data () {
    return {
      msg: 'Welcome to monitor.hplustime.com'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
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
  color: #35495E;
}
</style>
