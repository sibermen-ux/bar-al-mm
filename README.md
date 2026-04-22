<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Seni Seviyorum ❤️</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #fff5f5;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
            overflow-x: hidden;
        }

        .container {
            background: white;
            padding: 40px;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(255, 77, 109, 0.1);
            max-width: 600px;
            width: 100%;
            text-align: center;
            transition: all 0.5s ease;
        }

        .heart { font-size: 60px; color: #ff4d6d; margin-bottom: 10px; animation: pulse 1.5s infinite; }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        h1 { color: #ff4d6d; font-size: 26px; margin-bottom: 20px; }

        /* Senin Paragrafın - Odak Alanı */
        .odak-alani {
            background-color: #fff0f3;
            border-left: 5px solid #ff4d6d;
            padding: 30px;
            margin: 25px 0;
            border-radius: 15px;
            text-align: left;
            font-style: italic;
            color: #333;
            line-height: 1.8;
            font-size: 17px;
            box-shadow: inset 0 2px 10px rgba(0,0,0,0.02);
            white-space: pre-line; /* Satır boşluklarını korur */
        }

        .buttons { margin-top: 30px; position: relative; min-height: 80px; }
        
        button {
            padding: 15px 35px;
            font-size: 18px;
            font-weight: bold;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #yesBtn { background-color: #ff4d6d; color: white; box-shadow: 0 5px 15px rgba(255, 77, 109, 0.4); }
        #yesBtn:hover { transform: scale(1.1); background-color: #ff1a4a; }

        #noBtn { background-color: #dee2e6; color: #495057; position: absolute; left: 50%; transform: translateX(20px); }
    </style>
</head>
<body>

<div class="container" id="mainContainer">
    <div class="heart">❤️</div>
    <h1>Seni Çok Seviyorum...</h1>

    <div class="odak-alani">
        Sevgilim, son günlerde ciddi şekilde can sıkan olaylardan dolayı özür dilerim. Sana karşı pek çok hatam oldu, hepsinden pişmanım, tekrardan özür dilerim. Seni çok seviyorum ama şu an sana tüm içtenliğimle söylüyorum; o eski kavgalarımız artık olmayacak. Gerek benim hatalarım, gerek senin hataların düzelecek. 
        
        Seni çok çok seviyorum sevgilim, sen benim her şeyimsin ♥️😘 

        Bu da bizim sınavımızmış bebeğim. Allah insanları sınar, belki de bizi böyle bir sınava tabi tutan Allah'tır. Önemli olan bebişim çabalamak... İkimiz de çabaladıktan sonra, el ele baş başa olduktan sonra aşamayacağımız bir mesele yok. İleride çok güzel hayatımız olacak. E tabii ki bu yolda önümüze kayalar, taşlar, çukurlar çıkacak; birlikte o engelleri aşacağız. 

        Seni seviyorum delicesine kurban olduğum 🥰🥰🥰🥰
    </div>

    <p style="color: #888; font-weight: bold;">Her şeye yeniden, el ele devam edelim mi?</p>
    
    <div class="buttons">
        <button id="yesBtn" onclick="affedildi()">Evet ❤️</button>
        <button id="noBtn" onmouseover="moveButton()">Hayır</button>
    </div>
</div>

<script>
    function moveButton() {
        const x = Math.random() * (window.innerWidth - 150);
        const y = Math.random() * (window.innerHeight - 100);
        const btn = document.getElementById('noBtn');
        btn.style.left = x + 'px';
        btn.style.top = y + 'px';
        btn.style.position = 'fixed';
    }

    function affedildi() {
        // Konfeti yağmuru
        const duration = 5 * 1000;
        const animationEnd = Date.now() + duration;
        const defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 0 };

        function randomInRange(min, max) {
            return Math.random() * (max - min) + min;
        }

        const interval = setInterval(function() {
            const timeLeft = animationEnd - Date.now();
            if (timeLeft <= 0) return clearInterval(interval);
            const particleCount = 50 * (timeLeft / duration);
            confetti(Object.assign({}, defaults, { particleCount, origin: { x: randomInRange(0.1, 0.3), y: Math.random() - 0.2 } }));
            confetti(Object.assign({}, defaults, { particleCount, origin: { x: randomInRange(0.7, 0.9), y: Math.random() - 0.2 } }));
        }, 250);

        // İçerik değişimi
        document.getElementById('mainContainer').innerHTML = `
            <div class="heart">💖</div>
            <h1>İyi ki Varsın!</h1>
            <p style="font-size: 20px; color: #444;">Seni dünyadaki her şeyden çok seviyorum. <br> Teşekkür ederim aşkım!</p>
            <div style="font-size: 60px; margin-top: 20px;">👩‍❤️‍👨✨💍</div>
        `;
    }
</script>

</body>
</html>
