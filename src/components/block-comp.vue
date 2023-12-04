<template> 
<button v-if="show" @click="stoptimer()"> 
{{ text }}
</button>

</template>



<script>
export default{
    props:['delay'],
    data(){
        return{
            text:"click fast",
            timer:null,
            reaction:0,
            show:false,
        }
    },
    mounted(){
       setTimeout(()=>{
        this.show=true
        this.starttimer()
       },this.delay)
    },
 
    methods:{
starttimer(){
this.timer=setInterval(()=>{
    this.reaction +=10
},10)
},
stoptimer(){
clearInterval(this.timer)
console.log(this.reaction)
this.$emit('end',this.reaction)
}
    }
}

</script>
<style scoped>
button{
    height: 600px;
    width: 700px;
    font-size: 100px;
    font-weight: 900;
    border-radius:30px ;
}

</style>