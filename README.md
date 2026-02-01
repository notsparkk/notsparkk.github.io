<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Manya</title>
    <style>
        /* --- General Styling --- */
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background-color: #ffe6ea; /* Light Pink Background */
            color: #d6336c; /* Darker Pink Text */
            text-align: center;
            overflow: hidden; /* Prevents scrollbars for the balloon effect */
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        p {
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 30px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* --- Buttons --- */
        .btn {
            background-color: #ff4d79;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
            margin: 10px;
        }

        .btn:hover {
            background-color: #d6336c;
            transform: scale(1.1);
        }

        /* --- Images --- */
        .img-container {
            margin: 20px auto;
            max-width: 80%;
        }

        img {
            max-width: 300px;
            max-height: 400px;
            border-radius: 15px;
            border: 5px solid white;
            box-shadow: 0 4px 15px rgba(255, 77, 121, 0.3);
            margin: 10px;
        }

        .collage {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
        }

        /* --- Pages Logic --- */
        .page {
            display: none; /* Hidden by default */
            animation: fadeIn 1s ease-in-out;
            width: 100%;
            height: 100%;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 10;
            position: relative;
        }

        .active {
            display: flex; /* Only the active page is shown */
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- Balloons Animation --- */
        .balloon {
            position: absolute;
            bottom: -50px;
            background-color: rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            animation: floatUp 10s linear infinite;
            z-index: 1;
        }

        @keyframes floatUp {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-110vh); opacity: 0; }
        }

        /* Special text for the last letter */
        .letter-text {
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(214, 51, 108, 0.2);
            color: #333;
            font-style: italic;
        }
    </style>
</head>
<body>

    <div id="balloon-container"></div>

    <div id="page1" class="page active">
        <div class="img-container">
            <img src="hug.jpg" alt="Two people hugging" onerror="this.src='https://via.placeholder.com/300x400/ffb6c1/ffffff?text=Lovely+Photo'">
        </div>
        <h1>To my pasandida Mahila...</h1>
        <button class="btn" onclick="nextPage(2)">Open ❤️</button>
    </div>

    <div id="page2" class="page">
        <h1>For the smiles you bring...</h1>
        <div class="collage">
            <img src="gift1.jpg" alt="Gift 1" onerror="this.src='https://via.placeholder.com/200/ffb6c1/ffffff?text=Gift+1'">
            <img src="gift2.jpg" alt="Gift 2" onerror="this.src='https://via.placeholder.com/200/ffb6c1/ffffff?text=Gift+2'">
        </div>
        <p>Just a few memories of little things...</p>
        <button class="btn" onclick="nextPage(3)">Next 🎁</button>
    </div>

    <div id="page3" class="page">
        <h1>And the memories we make...</h1>
        <div class="collage">
            <img src="gift3.jpg" alt="Gift 3" onerror="this.src='https://via.placeholder.com/200/ffb6c1/ffffff?text=Gift+3'">
            <img src="gift4.jpg" alt="Gift 4" onerror="this.src='https://via.placeholder.com/200/ffb6c1/ffffff?text=Gift+4'">
        </div>
        <p>I hope you liked these!</p>
        <button class="btn" onclick="nextPage(4)">I have a question...</button>
    </div>

    <div id="page4" class="page">
        <h1>Manya, Will you be my valentine and promise to be with me forever ??</h1>
        
        <div style="margin-top: 30px;">
            <button class="btn" onclick="nextPage(5)">YES</button>
            <button class="btn" id="noBtn" onclick="rejectLove()">NO</button>
        </div>
    </div>

    <div id="page5" class="page">
        <div class="letter-text">
            <p>
                Thank you Manya for accepting this.I want you to know that you are the best thing that could happen to me in my life. You're the reason I could make it this far, and I promise to always be there for you. Ik that I've made some mistakes in the past 
                but I promise that everything will become better. <br><br>
                Thank you for being the peace of my life. I have a big favour to ask you. If you're free for the next 70 years or so, I want to ask you to be my lover and stay with me forever.
                I promise you to make your life the best.
            </p>
            <h3>Love,<br>Rajbir Singh</h3>
        </div>
    </div>

    <script>
        // Function to switch pages
        function nextPage(pageNumber) {
            // Hide all pages
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => page.classList.remove('active'));

            // Show the selected page
            const selectedPage = document.getElementById('page' + pageNumber);
            if (selectedPage) {
                selectedPage.classList.add('active');
            }
        }

        // Logic for the "NO" button on Page 4
        function rejectLove() {
            const noBtn = document.getElementById('noBtn');
            // Change text to "Not a chance !!"
            noBtn.innerText = "Not a chance !!";
            // Optionally make it unclickable or shake
            noBtn.style.backgroundColor = "#ff9999";
            
            // You can add a shake animation here if you want
            noBtn.style.transform = "translateX(10px)";
            setTimeout(() => { noBtn.style.transform = "translateX(-10px)"; }, 100);
            setTimeout(() => { noBtn.style.transform = "translateX(0)"; }, 200);
        }

        // Script to generate floating balloons
        function createBalloons() {
            const container = document.getElementById('balloon-container');
            const balloonCount = 20;

            for (let i = 0; i < balloonCount; i++) {
                const balloon = document.createElement('div');
                balloon.classList.add('balloon');
                
                // Randomize size and position
                const size = Math.random() * 30 + 20 + 'px';
                balloon.style.width = size;
                balloon.style.height = size;
                balloon.style.left = Math.random() * 100 + 'vw';
                balloon.style.animationDuration = Math.random() * 5 + 5 + 's';
                balloon.style.animationDelay = Math.random() * 5 + 's';
                
                // Randomize balloon colors (Pink, White, Red variations)
                const colors = ['#ff4d79', '#ffb3c6', '#ffffff', '#ff8099'];
                balloon.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];

                container.appendChild(balloon);
            }
        }

        // Initialize balloons on load
        createBalloons();
    </script>
</body>
</html>
