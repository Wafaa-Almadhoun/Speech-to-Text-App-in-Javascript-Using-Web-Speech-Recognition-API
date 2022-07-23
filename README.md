# Speech-to-Text-App-in-Javascript-Using-Web-Speech-Recognition-API



## Table of contents
* [Introduction](#Introduction)
* [Technologies](#technologies)
* [The codes](#the-codes)




## Introduction

 we will clear how to create voice to text converter. by create speech to text converter using HTML CSS and JavaScript


## Technologies
Project is created with:
* Visual studio code  [To Downloud](https://code.visualstudio.com/)
	
## The codes

### HTML

     <!DOCTYPE html>

     <html lang="ar">

     <head>

     <meta charset="utf-8">

     <meta name="viewport" content="initial-scale=1.0, maximum-scale=1.0, user-scalable=1">

     <title>Home</title>

     <link rel="stylesheet" type="text/css" href="style.css">

     </head>

     <body>

	<div class="voice_to_text"> 
	
		<h1>محول الصوت الى نص</h1>
		
        <textarea name="" id="convert_text"></textarea>
	
    <button id="click_to_record">اضغط للبدأ</button>
    
    </div>



     <script type="text/javascript" src="script.js"></script>

   </body>

   </html>


   
    
### CSS

      *,*:after,*:before{

	-webkit-box-sizing: border-box;
	
	-moz-box-sizing: border-box;
	
	-ms-box-sizing: border-box;
	
	box-sizing: border-box;
	
    }
    body{
	font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
	
	font-size: 16px;
	
	margin: 0;
	
	background:linear-gradient(to right bottom, #3cffe5, #031f6a);
	
	color: #000;
	
	
	display: flex;

      align-items: center;
  
       justify-content: center;
  
        min-height: 100vh;
  
    }

     .voice_to_text{

     width: 600px;
  
     text-align: center;
  
     letter-spacing: initial;
  
   }

   h1{

	color: #fff;
	
	font-size: 50px;
	
    letter-spacing: initial;
    
  }
   #convert_text{

    text-align: right;  
  
    width: 100%;
  
    height: 200px;
  
    border-radius: 10px;
  
    resize: none;
  
    padding: 10px;
  
    font-size: 20px;
  
    margin-bottom: 10px;
  
    letter-spacing: initial;
  
   }

   button{

     	padding: 12px 20px;
    	
    background: #000304;
  
     border: 0;
  
     color: #fff;
  
     font-size: 18px;
  
    cursor: pointer;
  
    border-radius: 5px;
  
   }


  

### JavaScript

    click_to_record.addEventListener('click',function(){
    
    var speech = true;
    
    window.SpeechRecognition = window.webkitSpeechRecognition;
    

    const recognition = new SpeechRecognition();
    
    recognition.lang = 'ar';
    
    recognition.interimResults = true;
    

    recognition.addEventListener('result', e => {
    
        const transcript = Array.from(e.results)
	
            .map(result => result[0])
	    
            .map(result => result.transcript)
	    
            .join('')

        document.getElementById("convert_text").innerHTML = transcript;
	
        console.log(transcript);
    });
    
    if (speech == true) {
        recognition.start();
    
    }
    
    })

![Capture](https://user-images.githubusercontent.com/64277741/180607258-9e2c643d-a29e-48a7-b0a1-475ab01ad6b9.PNG)
Figure (1): The result 
