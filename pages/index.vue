<template>
  <div>
    <h1 v-if="apiValue" class="font-bold text-1xl">Check: {{apiValue}}</h1>
    <button @click.prevent="testBackentRequest">Request Api</button>
    <Tutorial/>
  </div>
</template>

<script>
export default {
  data(){
    return{
      apiValue:''
    }
  },
  mounted() {

  },
  methods:{
    testBackentRequest(){
      this.$axios.get('/test').then(res=>{
        this.apiValue = res.data;
      });
    }
  }
}
</script>
