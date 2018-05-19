<template>
  <div id="app">
    <vigotech-member-list :members="vigotech.members"></vigotech-member-list>
  </div>
</template>

<script>
import VigotechMemberList from './components/VigotechMemberList'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    VigotechMemberList,
  },
  data() {
    return {
      vigotech: {},
    }
  },
  methods: {
    getMembers() {
      axios.get(process.env.VUE_APP_VIGOTECH_MEMBERS_SOURCE)
          .then(response => {
            this.vigotech = response.data
          })
          .catch(response => {
            alert(response.data)
          })
    }
  },
  mounted () {
    this.getMembers()
  }
}
</script>

<style lang="scss">
  body {
    font-family: 'Raleway', sans-serif;
  }
</style>