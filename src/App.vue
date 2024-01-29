<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()
let name = ref("Manolya")
let course = ref("Data Management")

let count = ref(0)

function increment() {
count.value ++;
}

function resetCount() {
    count.value = 0;
}

let text = ref("");
let inputText = ref("");
function addText() {
    text.value += inputText.value;
}
function resetText() {
    text.value = ""
}

let Selector = ref("");
let inputcolor = ref("");
function changebgcolor() {
    let element = document.querySelectorAll(Selector.value);
    element.forEach(element => {
        element.style.backgroundColor = inputcolor.value;
    });
}

</script>



<!-- the template is where the html code goes -->
<template>

<div id="navbar" class="container"> 
        <div id="title">Manolya Website</div>

        <div id="logo"> 
          <img src="./cow.jpg">
        </div>
            

    </div>

    
    <div id="flex">

      <div id="sidebar" class="container"> Sidebar
            <br>
            <button @click="increment">Count is: {{ count }}</button>
            <button @click="resetCount">Reset number</button>
            <br>
            <br>

            <!--creating new text -->
            <input v-model="inputText" type="text" placeholder="Type anything..." />
            <br>
            <button @click="addText"> Add text </button>
            <br>
            <br>
            <input v-model="Selector" type="text" placeholder="type: #navbar / #sidebar / #main" />
            <br>
            <input v-model="inputcolor" type="text" placeholder="Color" />
            <br>
            <button @click="changebgcolor">Apply Background Color</button>
        </div>

        <div id="main" class="container"> Text:
            <br>


            <p> {{ text }} </p>
            <br> <button @click="resetText">Reset text?</button>
        </div>
    </div>

</template>



<!-- style is where the css code goes -->
<style scoped>
html{
    background-color: black;
    color: white;
}

body{

    margin:0;
}

div{

    box-sizing: border-box;
}

img{
    height: 100%;
    width: auto;
}

#navbar{

    height: 50px;
    border-color: aquamarine;

}

#flex{

    display: flex;
    height: calc(100vh - 50px);

}

#sidebar{

    width: 30%;
    border-color: blue;
}

#main{

    width: 70%;
    border-color: blueviolet;

}

#title{
    width: 70%;
    float: left;
}

#logo{
    width: 30%;
    height: 100%;
    float: right;
    text-align: right;
}

.container{

    border-style: dotted;
    border-color: white;
    border-width: 1px;
}

</style>