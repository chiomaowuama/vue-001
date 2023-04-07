<script setup>
import { computed } from '@vue/reactivity';
import { ref } from 'vue';
// import logo from "./assets/logo.svg";


const input = ref(null);
const year = ref(null);

const result = computed(() => {
  return input.value;
});
const generation = computed(() => {
  // return year.value;
  if(year.value >= 1901 && year.value <= 1924){
    return {name:"This is the Greatest Generation",image:"/Benin.jpg"};
  }
  if(year.value >= 1925 && year.value <= 1945){
    return {name:"Generation: The Silent Generation",image:"/slavery.jpg"};
  }
  if(year.value >= 1946 && year.value <= 1964){
    return {name:"The Baby Boomer Generation",image:"/oldschool.jpg"};
  }
  if(year.value >= 1965 && year.value <= 1979){
    return {name:"The Generation X",image:"/thenext.jpg"};
  }
  if(year.value >= 1980 && year.value <= 1994){
    return {name:"Millennials", image:"/the90s.jpg"};
  }
  if(year.value >= 1995 && year.value <= 2012){
    return {name:"Generation Z ", image:"/the-genz.jpg"};
  }
  if(year.value >= 2013 && year.value <=2025){
    return {name:"Gen Alpha " ,image:"/emo.jpg"};
  }
  else{
    return{name:"The Name of the Generation shows here",image:"/logo.svg"}
  }
});
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <div class="wrapper">
      <div class="the-first-wrap">
        <div class="the-left">
          <div class="the-form">
            <div class="the-n up">
              <label for="name">NAME:</label>
              <input type="text" v-model="input" >
            </div> <div class="the-n down">
              <label for="name">D O B :</label>
              <input type="number" v-model="year" @input="() => { if(year > 1990 && year < 0) { year = 1990 }}">
            </div>
          </div>
        </div>
        <div class="the-right-side">
          <div class="right-cover">
            <h1>Welcome:{{ result }}</h1>
            <p class="gen">  {{ generation?.name }}</p>
            <div class="dif-image">
                <img alt="Vue logo" class="logo" :src="generation?.image " width="125" height="125" />
            </div>
          </div>
          <div class="the-greetings">
            <h5>Yours Truely, Mobiana  <font-awesome-icon :icon="['fas', 'heart']" style="color: #ef0629;" /></h5>

          </div>
        </div>
      </div>
    </div>
  </header>

  
</template>

<style >
body{
  margin:0px;
  padding:0px;
  overflow:hidden;
}
.wrapper{
  border:2px solid rgb(100, 10, 10);
  /* background-color: black; */
  min-height:95vh;
  padding:10px 0;
  display:flex;
  justify-content: center;
  align-self: center;


 
}
.the-first-wrap{
  width:98%;
  min-height:80%;
  background-color: white;
  border:2px solid black;
  display:grid;
  grid-template-columns: 5fr 7fr;
 
}
.the-left{
  /* border:2px solid black; */
  display:flex;
  justify-content: center;
  align-items: center;
}
.the-form{
  border:2px solid black;
  box-shadow: 3px 5px 15px -1px #888888;
  width:70%;
  height: 80%;
}
.the-n{
  /* border:2px solid blue; */
  width:100%;
  display:flex;
  justify-content: space-around;
  align-items: center;
  text-align: center;
}
.up {
  margin-top:20%;
  padding:10px 0;
}
label{
  font-size:20px;
  font-weight: 600;
}
input{
  outline:none;
  border:1px solid black;
  border-left:none;
  border-right:none;
  border-top:none;
  width:55%;
  cursor:text;
  font-size: 15px;
  font-weight:600;
  padding:5px 0;
  text-transform: capitalize;
}
.down {
  margin-top:20%;
  padding:10px 0;
}
/* .the-right-side{
  
  
} */
.dif-image{
  /* border:2px solid black; */
  width:120%;
  height:150px;
  /* box-shadow: 3px 5px 15px -1px #888888; */
}
.logo{
  width:100%;
  height:100%;
}
.right-cover{
  display: grid;
  justify-content: center;
  align-items: center;
  /* border:2px solid red; */
  min-height:95%;
  text-transform: capitalize;
}
.the-greetings h5{
  /* border:2px solid green; */
  padding:0px;
  margin:0px;
  
}
.gen{
  /* border:2px solid red; */
  font-size: 20px;
  font-weight:800;
  /* word-spacing: 0.5rem;; */
}
@media (min-width: 600px) {
  .dif-image{
  /* border:2px solid black; */
  width:80%;
  height:150px;
  /* box-shadow: 3px 5px 15px -1px #888888; */
}
.logo{
  width:100%;
  height:100%;
}
}
 
</style>
