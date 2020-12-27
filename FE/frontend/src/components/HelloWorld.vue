<template>
  <div class="parent">
      <div class="first">
        <div class="fleft">
          left
        </div>
        <div class="fright">
          right
        </div>
        
      </div>
    <div class="second">
      <div class="allmid">
        <div class="sleft">
          left
        </div>
        <div class="scenter">
          <button v-on:click="greet()">click here</button>
        </div>
        <div class="sright">
          right
        </div>
        
      </div>
       <div class="sunder">
          under
        </div>
    </div>
    <div class="third">
      sfsdf
    </div>
  </div>
</template>

<script>


export default {
  name: 'HelloWorld', 
  data: function () {
    return {
      count: 0
    }
  }, 
  props: {
    msg: String,
  },
  methods: {
    greet: function () {
      
      this.abc();
    },
    number: function(num){
      
      return num;
    },
    abc: function() {
      
         for(let i=0;i<=11;i++)
         {
           if(i%i==0)
           {
             console.log(i)
           }
         }
        
         
      
    }
  }

 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
  color: #42b983;
}

.parent {
  height:100%;
}
.first {
 height: 20% ;
 background-color: red;
 display: inline-flex;
 width: 100%;
}
.second {
  text-align: center;
 height: 60% ;
 background-color:blue;
 display: block;
 width: 100%;
}
.third {
  text-align: right;
 height: 20% ;
 background-color:green
}
.fleft {
  text-align: left;
  width: 50%;
  
}
.fright {
  text-align: right;
  width: 50%;
  
}
.sleft {
  text-align: left;
  width: 100%;
  border: 2px solid black;
}
.scenter {
  text-align: center;
  width: 100%;
  border: 2px solid black;
}
.sright {
  text-align: right;
  width: 100%;
  border: 2px solid black;
}
.allmid {
  display: inline-flex;
  width: 100%;
  height: 50%;
}
.sunder {
  height: 50%;
  border: 2px solid black;
}
</style>
