<template>
  <div class="vigotech-member-list">
    <div class="container">
      <div class="row">
        <vigotech-member
            class="col-xs-12 col-sm-4 col-md-3"
            v-for="(member, key) in members"
            :member="member"
            :key="key"
        ></vigotech-member>
      </div>
    </div>
  </div>
</template>

<script>
import VigotechMember from "./VigotechMember";
export default {
  name: 'vigotech-member-list',
  components: {
    VigotechMember
  },
  props: {
    members: {
      type: [Array, Object],
      required: true
    }
  },
}
</script>

<style scoped lang="scss">

</style>
