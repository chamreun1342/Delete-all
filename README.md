<html>
<head>
<meta charset="UTF-8">
<title>Message Share Tool</title>

<style>
body{
font-family:Arial;
background:#111;
color:white;
text-align:center;
padding:30px;
}

textarea,input{
width:85%;
padding:10px;
margin:10px;
border-radius:8px;
border:none;
}

button{
padding:12px 25px;
margin:10px;
border:none;
border-radius:8px;
font-size:16px;
cursor:pointer;
}

.generate{
background:#ff3b3b;
color:white;
}

.share{
background:#2ecc71;
color:white;
}

#output{
margin-top:20px;
background:#222;
padding:15px;
border-radius:10px;
height:200px;
overflow:auto;
}
</style>

</head>

<body>

<h2>MATIN</h2>

<textarea id="message" placeholder="Write message"></textarea>

<br>

<input type="number" id="count" placeholder="Number (100 / 10000)">

<br>

<button class="generate" onclick="generate()">Generate</button>

<button class="share" onclick="shareMsg()">Share</button>

<div id="output"></div>

<script>

let finalMessage="";

function generate(){

let msg=document.getElementById("message").value;
let count=document.getElementById("count").value;

finalMessage="";
let out="";

for(let i=1;i<=count;i++){
finalMessage += msg + "\n";
out += i+". "+msg+"<br>";
}

document.getElementById("output").innerHTML=out;

}

function shareMsg(){

if(navigator.share){

navigator.share({
title:"Message",
text:finalMessage
});

}else{

alert("Your browser does not support share");

}

}

</script>
