<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Angelie's Enchanted Eighteen</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Mrs+Saint+Delafield&display=swap" rel="stylesheet">

    <style>
        body {
            margin: 0;
            padding: 0;
            background: url('background.jpg') no-repeat center center fixed;
            background-size: cover;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            font-family: 'Arial', sans-serif;
            overflow-x: hidden;
        }

        h1 {
            font-family: 'Mrs Saint Delafield', cursive;
            font-size: 5rem;
            color: #f1e5ac;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.8), 0 0 20px rgba(212, 175, 55, 0.5);
            margin: 20px 0;
            text-align: center;
        }

        .instruction {
            color: #fff;
            background: rgba(0, 0, 0, 0.4);
            padding: 5px 15px;
            border-radius: 20px;
            margin-bottom: 20px;
            font-size: 0.9rem;
            letter-spacing: 1px;
            border: 1px solid #d4af37;
        }

        /* The Flip Container */
        .flip-card {
            background-color: transparent;
            width: 400px;
            height: 600px;
            perspective: 1000px; /* Essential for 3D effect */
            cursor: pointer;
        }

        /* This inner container handles the flip animation */
        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            text-align: center;
            transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
            transform-style: preserve-3d;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
            border-radius: 15px;
        }

        /* The actual flip action happens here */
        .flip-card.flipped .flip-card-inner {
            transform: rotateY(180deg);
        }

        /* Front and Back styling */
        .flip-card-front, .flip-card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden; /* Safari */
            backface-visibility: hidden;
            border-radius: 15px;
            border: 2px solid #d4af37;
            overflow: hidden;
        }

        .flip-card-front img, .flip-card-back img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Style for the back side */
        .flip-card-back {
            transform: rotateY(180deg);
        }

        @media (max-width: 450px) {
            .flip-card {
                width: 90vw;
                height: 135vw;
            }
            h1 { font-size: 3.5rem; }
        }
    </style>
</head>
<body>

    <h1>Angelie's Enchanted Eighteen</h1>
    
    <div class="instruction">Tap or Click to Flip</div>

    <div class="flip-card" id="myCard">
        <div class="flip-card-inner">
            <div class="flip-card-front">
                <img src="invitation_front.png" alt="Invitation Front">
            </div>
            <div class="flip-card-back">
                <img src="invitation_back.png" alt="Invitation Back">
            </div>
        </div>
    </div>

    <script>
        const card = document.getElementById('myCard');
        card.addEventListener('click', function() {
            card.classList.toggle('flipped');
        });
    </script>

</body>
</html>
