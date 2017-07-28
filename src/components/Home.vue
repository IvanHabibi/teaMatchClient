<template>
  <div>
    <Facebook></Facebook>
    <Google></Google>
  </div>
</template>

<script>
import Facebook from './Facebook'
import Google from './Google'

export default {
  name: 'Home',
  components: {
 Facebook,Google
  },
  data() {
    return {
    }
  },
  methods: {
  },
  mounted() {

  }
}
</script>


<style scoped lang='css'>

</style>
