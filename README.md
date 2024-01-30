<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Theory Assignment:-1</title>
  <style>
    body{
      color:yellow;
      background-color: #FFFF00;
    }
     .bg-color{
      background-color: #FFFF00;
    }
    .interface{
      margin-left:60%;
      width:30%;
      text-align: center;
    }
   .margin{
      margin-bottom:5px;
    }
  .align{
      margin-left:55%;
      margin-bottom:5px;
    }
  .logo{
      margin-top:10px;
      margin-left:10px;
      position:absolute;
      z-index:10;
      width:25vw;
      height:15vh;
    }
  .container{
      text-align:center;
      width:27%;
      position:absolute;
      z-index:2;
      margin-top:100px;
    }
   .container1{
      width:64%;
      height:409px;
      margin-left:30%;
      background-color:#D7BDE2;
      color:black;
    }
  .button{
      border-radius: 16px;
      width:170px;
      height:50px;
      margin-bottom: 20px;
      margin-left:10px;
      transition: 0.3s;
    }
   .button:hover{
      background-color: #E8DAEF;
      color: black;
    }
   #Op1{
      margin-left:40%;
    }
   #Op2{
      margin-left:40%;
    }
  #Op3{
      margin-left:40%;
    }
  #Op4{
      margin-left:40%;
    }
  a{
      text-decoration: none;
      color:black;
    }
  .final{
      display:flex;
      color:black;
      font-size:1.5rem;
      justify-content: center;
      flex-direction:column;
    }
   .reset{
      margin-left:3vw;
      margin-top:5vh;
      color:black;
    }
  </style>
</head>
<body>
<img class="logo" src="https://raw.githubusercontent.com/Legendary-Person/OS_LAB/main/KIIT%20Logo%20Silver%20Jubilee%2025%20Years-.png" alt="KIIT silver">

<article>
  <header>
    <div class="align" style="font-size:4.75rem;">Form</div>
  </header>
</article>

<div class="container bg-color">
  <button class="button" style="margin-top:20px;" type="button" onclick="showContent(1)">Button 1</button><br>
  <button class="button" type="button" onclick="showContent(2)">Button 2</button><br>
  <button class="button" type="button" onclick="showContent(3)">Button 3</button>
</div>

<div class="container1">
  <br><br><br>

  <div id="content1" class="content" style="margin-top:110px;">
    <form id="form1">
      <label for="fname" style="margin-left:30%;">First Name: </label>
      <label>
        <input id="fname" type="text" name="fname" value="John">
      </label><br><br>
      <label for="lname" style="margin-left:30%;"> Last Name:‎ </label>
      <label>
        <input id="lname" type="text" value="Doe" name="lname">
      </label>
    </form>
  </div>

  <div id="content2" class="content" style="display:none;">
    <form id="form2" style="margin-top:100px;">
      <p style="margin-left:45%; margin-bottom:8px;">
    <input id="html" name="language" type="radio" value="HTML">
        <label for="html">HTML</label><br>
   <input id="css" name="language" type="radio" value="CSS">
        <label for="css">CSS</label><br>
   <input id="js" name="language" type="radio" value="JavaScript">
        <label for="js">JavaScript</label><br>
  <input id="Jv" name="language" type="radio" value="Java">
        <label for="Jv">Java</label>
      </p>
    </form>
  </div>
  <div id="content3" class="content" style="display:none;">
    <form id="form3">
      <div style="margin-top:90px;">
        <div>
          <label for="Op1"></label><input type="checkbox" name="check" id="Op1" value="mango">
          <label>i like mango</label>
        </div>
        <br>
        <div>
          <label for="Op2"></label><input type="checkbox" name="check" id="Op2" value="orange">
          <label type="checkbox">I like apple</label>
        </div>
        <br>
        <div>
          <label for="Op3"></label><input type="checkbox" name="check" id="Op3" value="orange">
          <label type="checkbox">I like orange</label>
        </div>
        <br>
        <div>
          <label for="Op4"></label><input type="checkbox" name="check" id="Op4" value="lichu">
          <label type="checkbox">I like lichu</label>
        </div>
      </div>
    </form>
  </div>
</div>

<div style="margin-top:5px;">
  <div class="interface">
    <button onclick="nextButton()">Next</button>
    <button type="submit" onclick="submitForms()" style="margin-left:20px;">Submit</button>
  </div>
</div>

<script >

  function showContent(c){
    let contents = document.getElementsByClassName('content');
    for(let i=0;i<contents.length;i++){
      contents[i].style.display='none';
    }
    document.getElementById('content'.concat(c)).style.display='block';
  }

  let counter=1;
  function nextButton(){
    if(counter===3){
      let ele=document.getElementById(`content${1}`);
      document.getElementById(`content${3}`).style.display='none';
      ele.style.display='block';
      counter=1;
    }else{
      counter++;
      let ele=document.getElementById(`content${counter}`);
      document.getElementById(`content${counter-1}`).style.display='none';
      ele.style.display='block';
    }
  }


  submitForms = function(){
    document.getElementById("form1").submit();
    document.getElementById("form2").submit();
    document.getElementById("form3").submit();

    const form1 = new FormData(document.getElementById("form1"));
    const form2 = new FormData(document.getElementById("form2"));
    const form3 = new FormData(document.getElementById("form3"));

    const asString1 = new URLSearchParams(form1).toString();
    const asString2 = new URLSearchParams(form2).toString();
    const asString3 = new URLSearchParams(form3).toString();

    document.write('<div style="margin-left:2vw; margin-top:5vh; margin-bottom:5vh; font-size:5rem;"><i><u>Form Information</u></i></div>')
    document.write('<div style="margin-left:3vw; font-size:2rem;">First Name‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ :<b>'+' '+asString1.split('&')[0].split('=')[1]+'</b></div>');
    document.write('<br>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">Last Name‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ :<b>'+' '+asString1.split('&')[1].split('=')[1]+'</b></div>');
    document.write('<br>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">Prog Language :<b>'+' '+asString2.split('=')[1]+'</b></div>');
    document.write('<br>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">Vehicles:</div>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">1. <b>'+asString3.split('&')[0].split('=')[1]+'</b></div>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">2. <b>'+asString3.split('&')[1].split('=')[1]+'</b></div>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">3. <b>'+asString3.split('&')[2].split('=')[1]+'</b></div>');
    document.write('<div style="margin-left:3vw; font-size:2rem;">4. <b>'+asString3.split('&')[3].split('=')[1]+'</b></div>');
  }
</script>
</body>
</html>
