![HackerRank](Binary%20Calculator/images/HackerRank.png)
<br/>
### This readme is made for 10 Days of JavaScript tutorials. <br/> 
## Day 9: Binary Calculator
<hr>

![HackerRank](Binary%20Calculator/images/image01.png)
![HackerRank](Binary%20Calculator/images/image02.png)
* HTML <br/>
```HTML
<div id="res"></div>
    <div id="btns">
        <button id="btn0">0</button>
        <button id="btn1">1</button>
        <button id="btnClr">C</button>
        <button id="btnEql">=</button>
        <button id="btnSum">+</button>
        <button id="btnSub">-</button>
        <button id="btnMul">*</button>
        <button id="btnDiv">/</button>
    </div>
```
![HackerRank](Binary%20Calculator/images/image03.png)
* CSS <br/>
```css
body{
    width: 33%;
}
#res{
    background-color: lightgray;
    border: solid;
    height: 48px;
    font-size: 20px;
}
#btn0, #btn1{
    background-color: lightgreen;
    color: brown;
}
#btnClr, #btnEql{
    background-color: darkgreen;
    color: white;
}
#btnSum, #btnSub, #btnMul,#btnDiv{
    background-color: black;
    color: red;
}
button{
    width: 25%;
    height: 36px;
    font-size: 18px;
    margin: 0px;
    float: left;
}
```
![HackerRank](Binary%20Calculator/images/image04.png)
![HackerRank](Binary%20Calculator/images/image05.png)
### My output <hr>
![HackerRank](Binary%20Calculator/images/image6.png)
![HackerRank](Binary%20Calculator/images/image07.png)

* JavaScript <br/>
```javascript
let buttons=document.querySelectorAll("button");
let screenValue=document.getElementById("res");

for(let item of buttons){
    item.addEventListener("click",function(e){
        let value=e.target.innerText;
        // console.log(value); value checked with console

        if(value==='C'){
            screenValue.innerHTML="";
            value="";
        }
        else if(value==="="){
            value=eval(screenValue.innerHTML.replace(/([01]+)/g,'0b$1')).toString();
            screenValue.innerHTML=Number(value).toString(2);
        }
        else{
           screenValue.innerHTML+=value; 
        }
    })
};
```