<template>
  <div class="parent">
      <div class="first"> 
        <div class="fleft">
          <img src="https://image.ibb.co/e0RLzK/entrepreneur_1340649_340.jpg" style="width:30%px; height:100%;"/>
        </div>
        <div class="fright">
           <button style="margin-left: 90%;">Nhập</button> 
           <button style="margin-left: 90%;">Xuất</button>
        </div>
        
      </div>
    <div class="second">
      <div class="allmid">
        <div class="sleft">
          left
        </div>
        <div class="scenter">
          <button v-on:click="greet()">click here</button>
          <div>
              <span v-for="text in textarr" v-bind:key="text"> 
              {{ text.textarr }} 
              </span>
          </div>            
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
      <img src="https://image.ibb.co/e0RLzK/entrepreneur_1340649_340.jpg" style="width:20%; height:100%;"/>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'HelloWorld', 
  data: function () {
    return {
      textarr:[
          
      ]
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
      axios.get('https://cat-fact.herokuapp.com/facts')
        .then(function (response) {
          // handle success
            let data1=response.data;
            
            for(let i=0;i<data1.length;i++)
            {           
              console.log(data1[i].text);
              this.textarr[i]=data1[i].text;             
            }           
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .then(function () {
          // always executed
        });
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
 height: 22% ;
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
  text-align: center;
 height: 20% ;
 background-color:green
}
.fleft {
  text-align: left;
  width: 50%;
  
}
.fright {
  width: 50%;
  display: grid ;
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
