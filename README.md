<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        body { background-color: #ffeef2; font-family: 'Kanit', sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; overflow: hidden; }
        .container { text-align: center; background: white; padding: 50px; border-radius: 30px; box-shadow: 0 15px 35px rgba(255, 77, 109, 0.2); z-index: 1; }
        h1 { color: #ff4d6d; font-size: 2.5rem; }
        p { color: #555; font-size: 1.2rem; }
        .buttons { margin-top: 30px; display: flex; justify-content: center; gap: 20px; }
        button { padding: 15px 30px; font-size: 1.2rem; border-radius: 50px; border: none; cursor: pointer; transition: 0.3s; }
        #yesBtn { background: #ff4d6d; color: white; }
        #noBtn { background: #ddd; color: #555; position: absolute; }
        .heart { position: fixed; color: #ff4d6d; font-size: 20px; animation: fall linear infinite; z-index: 0; }
        @keyframes fall { to { transform: translateY(110vh); } }
    </style>
</head>
<body>

    <div class="container">
        <h1 id="title"></h1>
        <p id="desc"></p>
        <div class="buttons">
            <button id="yesBtn">อย่ากด ❤️</button>
            <button id="noBtn">ควยไผ่ 😜</button>
        </div>
    </div>

    <script>
        const CONFIG = {
            partnerName: "Happy Valentine", // แก้ชื่อแฟนตรงนี้
            yourName: "",        // แก้ชื่อคุณตรงนี้
            messages: {
                subtitle: "รักพวกมีง ✨",
                loveNote: "บ่าห่าบันต๋ายนี่หน้าอย่างวอก!"
            }
        };

        // แสดงผลข้อมูล
        document.getElementById('title').innerText = "ถึง... " + CONFIG.partnerName;
        document.getElementById('desc').innerText = CONFIG.messages.subtitle + "\n" + CONFIG.messages.loveNote;

        const yesBtn = document.getElementById('yesBtn');
        const noBtn = document.getElementById('noBtn');

        // ฟีเจอร์ 1: ปุ่ม No วิ่งหนี
        noBtn.addEventListener('mouseover', () => {
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight);
            noBtn.style.left = `${x}px`;
            noBtn.style.top = `${y}px`;
        });

        // ฟีเจอร์ 2: กดตกลงแล้วใจฟู
        yesBtn.addEventListener('click', () => {
            alert("กดทำควยไร ❤️ " + CONFIG.yourName + " ไอควาย");
            location.reload(); // รีโหลดหน้าเว็บ
        });

        // ฟีเจอร์ 3: หัวใจโปรยปราย
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerText = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';
            heart.style.opacity = Math.random();
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 300);
    </script>
</body>
</html>
