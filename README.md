<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>quote-Generator</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Open+Sans">
    <style>
        :root{
            font-size: 20px;
            font-family: 'Open Sans', Arial;
        }
        body{
            height: 95vh;
            background-color: coral;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
        }
        .main-content{
            background-color: white;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            max-width: 50vw;
            min-width: 20vw;
        }
        .quote{

        }
        #content{
            font-size: 1.1rem;
        }
        #author{
            font-size: 1.5rem;
        }
        #newQuote{
            display: inline-block;
            padding: 10px 15px;
            font-size: 1rem;
            margin: auto;
            color: white;
            background-color: #222222;
            border-radius: 5px;
            border: none;

            transition: transform 300ms ease-out;
        }
        #newQuote:hover{
            transform: scale(1.1);
        }
    </style>
</head>
<body>
    <div class="main-content">
        <div class="quote">
            <p id="content">“Two things are infinite: the universe and human stupidity; and I'm not sure about the universe.”</p>
            <p id="author">Albert Einstein</p>
        </div>
        <button id="newQuote">new quote</button>
    </div>
    <script>
    // get Elements
    const content = document.getElementById('content');
    const author = document.getElementById('author');
    const button = document.getElementById('newQuote');

    const api_url = 'https://api.quotable.io/random';

    async function newQuote(){
        const response = await fetch(api_url);
        const data =  await response.json();
        content.innerText = data.content;
        author.innerText = data.author;
    }
    button.addEventListener('click', function() {
        newQuote();
    })

    </script>
</body>
</html>
