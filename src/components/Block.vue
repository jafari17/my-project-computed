

<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click me</div>
</template>


<script >
import {onMounted} from "vue";

export default {
  props:['dalay'],
  data(){
    return{
      showBlock: false,
      timer: null,
      reactionTimer: 0,
    }
  },
  mounted(){
    console.log("componet mounted")
    setTimeout(() => {
    this.showBlock = true
    this.startTimer()
    console.log(this.delay);
                            }, this.dalay)
  },
  methods:{
    startTimer(){
      this.timer = setInterval(() => {
        this.reactionTimer += 10
      }, 10)
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end', this.reactionTimer)
      console.log(this.reactionTimer);
    },
  }

}

</script>


<style scoped>
.block{
  width: 400px;
  border-radius: 20px;
  background: greenyellow;
  color: #fff;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>