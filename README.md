﻿# Scramble-word-game
Skip to content
Search or jump to…
Pull requests
Issues
Marketplace
Explore
 
@praveenme117 
praveenme117
/
Scramble-word-game
Public
Code
Issues
Pull requests
Actions
Projects
Wiki
Security
Insights
Settings
Scramble-word-game/word scramble game.html
@praveenme117
praveenme117 Add files via upload
Latest commit 31b7525 1 minute ago
 History
 1 contributor
188 lines (157 sloc)  5.63 KB

<!DOCTYPE html>
<html>
    <head>
        
    <title></title>
    <link href="https://fonts.googleapis.com/css2?family=Carter+One&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@1,600&display=swap" rel="stylesheet">
    <style>
        *{ margin: 0; padding: 0; box-sizing: border-box;}

        header{
            width:100%;
            height:15vh;
            background-color: #20bf6b;
            }

            h1{
                font-family: 'Carter One' , cursive;
                text-align: center;
                color: white;
                font-size: 1.8rem;
                font-family: 'Carter One', cursive;
                letter-spacing: 15px;
                text-shadow: : 0 1px 0 #efefef,
                               0 2px 0 #efefef,
                                0 3px 0 #efefef,
                                0 4px 0 #efefef,
                                0 30px 5px rgba(0,0,0,.1);

            }

            section{
                height: 85vh;
                display: flex;
                justify-content: center;
                align-items: center;
                background-color: #7bed9f;

            }

            .gameArea{
                width: 50%;
                height: 400px;
                padding: 20px 0;
                background-color: #2ed573;
                display: flex;
                flex-direction: column;
                justify-content: center;
                align-items: center;
                box-shadow: 0 8px 6px -6px black;
                font-family: 'Source Sans Pro', sans-serif;
                box-shadow:  0 8px 6px -6px black;
                
            }

            h3{
                text-align: center;
                font-size: 1.5rem;
            }

            input{
                width: 40%;
                padding: 15px 0;
                text-align: center;
                border-radius: 25px;
                outline: none;
                border: none;
                background-color: #dff9fb;
                color: black;
                margin: 2rem 0;
                font-size: 1.1rem;

            }

            button{
                font-size: 1rem;
                cursor: pointer;
                outline: none;
                border: #2f3542;
                text-decoration: none;
                margin-top: 10px;
                color: #eb4d4b;
            }

            button.btn
            {
                font-weight: 600;
                padding: 1rem 2rem;
                background: white;
                text-transform: uppercase;
                transition-property: all;
                transition-duration: 0.5s;
                transition-timing-function: cubic-bezier(0.65, -0.25, 0.25, 1.95);

            }

            button.btn:hover, button.btn:focus, button.btn:active
            {
                letter-spacing: 0.125rem;
                word-spacing: 0.2rem ;

            }

            /* .hidden{
               display: none;
            } */

    </style>
    
    </head>
    <body>
        <header>
            <h1>Guess the word Game</h1>

        </header>
        
        <section>
            <div class="gameArea">
                <h3 class="msg"></h3>
                <input type="text" class="hidden">
                <button class="btn"> Click here to start</button>    

            </div>
        </section>
        <script>

            const msg= document.querySelector('.msg');
            const guess = document.querySelector('input');
            const btn = document.querySelector('.btn');
            let play = false;
            let sWords= ['python', 'javascipt', 'c++', 'php','java', 'c#', 'html', 'css', 'reactjs', 'angular', 'swift', 'android', 'sql'];

            const createNewWords = () =>
            {
                 let ranNum=Math.floor(Math.random() * sWords.length);
                // console.log(ranNum)
                 let newTempSwords=sWords[ranNum];
                 //console.log(newTempSwords.split(""));
                  return newTempSwords;
               

            }

           const scrambleWords = (arr) =>{
            for(let i=arr.length-1;i>=0;i--)
            {
                let temp=arr[i];
                console.log(temp);
                let j= Math.floor(Math.random()*(i+1));
                // console.log(i);
                // console.log(j); 
                arr[i]= arr[j];
                arr[j]=temp;
            }
            return arr;
           }
            btn.addEventListener('click', function()
            {
            if(!play){
                play=true;
                btn.innerHTML= "Guess";
                guess.classList.toggle('hidden');
                 newWords= createNewWords();
                 randWords=scrambleWords(newWords.split("")).join("");
              // console.log(randWords.join(""));
               msg.innerHTML= `Guess the word: ${randWords}`;
            }
               else{
                let tempWord=guess.value;
                if(tempWord === newWords)
                {
                play = false;
                msg.innerHTML=`Awesome its correct.it is ${newWords}`;
                btn.innerHTML="Start again";

               }
               else{
                msg.innerHTML=`sorry boss .it is incorrect . plz try again ${randWords}`;
                btn.innerHTML="Try again";
                
               }

            }
            
            })
        </script>
    </body>
</html>
© 2022 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
Loading complete
