
<template>
<p>Reation {{ this.score}} ms</p>
</template>


<script >
export default {
  props:['score'],
  data() {
    return {
    }
  },
   mounted(){
    console.log(this.score)
   }

}

</script>

<style scoped>

</style>