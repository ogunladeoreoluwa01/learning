<template>
    <h3> your time was {{scores}} ms <span :class="stylesObj">{{ thought }} </span></h3>
</template>
<script>

export default{
    props:['score'],
    data(){
        return{
           scores:this.score,
           fast:false,
           red:false,
           okey:false,
        }
    },
    computed:{
    stylesObj() {
        if (this.scores > 900) {
            return { red: true };
        } else if (this.scores <=600 ) {
            return { okey: true };
        } else if (this.scores <=400){
            return { fast: true };

        }
        return {}
    },

    thought() {
        if (this.stylesObj.red) {
           
            return "could work on your time ";
        } else if (this.stylesObj.okey) {
            
            return "alright your getting there";
        } else if (this.stylesObj.fast) {
          
            return "ohh your zoomin";
        }

        return "Default reaction";
    },

   
},
}

</script>
<style scoped>
h1{
    font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.red{
color: red;
}
.okey{
color: orange;
}
.fast{
color: greenyellow;
}




</style>
