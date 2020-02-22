<template>
  <ul>
    <li v-for="(user) in users" :key="user.id">
      <a href="#">{{user.id}}:{{user.name}}</a>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      users: []
    }
  },
  mounted () {
    axios.get('/api/users').then(res => {
      this.users = res.data
    })
  }
}
</script>
