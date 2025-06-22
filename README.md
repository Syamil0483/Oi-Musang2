# Oi-Musang2
SINI MAIN
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Jual Beli Musang - Seru-seruan!</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Comic+Neue:wght@400;700&display=swap');
    body {
      margin: 0;
      font-family: 'Comic Neue', cursive;
      background-color: #fefbd8;
      color: #333;
      overflow-x: hidden;
    }
    .container {
      max-width: 700px;
      margin: 30px auto;
      background-color: #fff;
      padding: 30px;
      border-radius: 25px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
      text-align: center;
      position: relative;
    }
    header img {
      max-width: 140px;
      border-radius: 15px;
      margin-bottom: 15px;
    }
    h1 {
      color: #d97706;
      font-size: 26px;
      margin-bottom: 10px;
    }
    .buttons {
      margin-top: 20px;
    }
    .buttons button {
      padding: 12px 24px;
      font-size: 16px;
      font-weight: bold;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      margin: 10px;
    }
    #yesButton {
      background-color: #facc15;
      color: #78350f;
    }
    #noButton {
      position: absolute;
      background-color: #fcd34d;
      color: #78350f;
    }
    form {
      text-align: left;
      margin-top: 20px;
    }
    .question-block {
      margin-bottom: 20px;
    }
    label {
      font-weight: bold;
      display: block;
      margin-bottom: 6px;
      color: #c2410c;
    }
    textarea {
      width: 100%;
      padding: 10px;
      font-size: 15px;
      border-radius: 10px;
      border: 1px solid #ccc;
      font-family: 'Comic Neue', cursive;
    }
    .navigation-buttons {
      display: flex;
      justify-content: space-between;
      margin-top: 20px;
    }
    .nav-button {
      padding: 10px 20px;
      border-radius: 12px;
      font-weight: bold;
      cursor: pointer;
      background-color: #fde68a;
    }
    .page {
      display: none;
    }
    .page.active {
      display: block;
    }
    button[type="submit"] {
      display: block;
      width: 100%;
      padding: 15px;
      font-size: 16px;
      font-weight: bold;
      color: white;
      background: linear-gradient(to right, #fbbf24, #f59e0b);
      border: none;
      border-radius: 20px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="container" id="introContainer">
    <img src="https://media.tenor.com/fS4T5LbWgqUAAAAi/cute-hamster.gif" alt="Cute Gif" />
    <h1>Halo Warga Jual Beli Musang! 🐾</h1>
    <p>Mau main game pertanyaan absurd buat kita makin deket dan ngakak-ngakak?</p>
    <div class="buttons">
      <button id="yesButton">Gaskeun! 😆</button>
      <button id="noButton">Ogah ah 😒</button>
    </div>
  </div>

  <div class="container" id="formContainer" style="display:none;">
    <form action="https://formspree.io/f/mwpbrepw" method="POST">
      <div id="page-1" class="page active">
        <div class="question-block"><label>1. Kalau kamu jadi hewan 1 hari, kamu mau jadi apa dan ngapain aja?</label><textarea name="q1"></textarea></div>
        <div class="question-block"><label>2. Siapa yang paling mungkin jadi presiden negara musang, dan kenapa?</label><textarea name="q2"></textarea></div>
      </div>
      <div id="page-2" class="page">
        <div class="question-block"><label>3. Kalau kita liburan bareng, siapa yang bakal nyasar duluan?</label><textarea name="q3"></textarea></div>
        <div class="question-block"><label>4. Zombie apocalypse: siapa yang survive terakhir?</label><textarea name="q4"></textarea></div>
      </div>
      <div id="page-3" class="page">
        <div class="question-block"><label>5. Kalau semua jadi makanan, kamu jadi makanan apa?</label><textarea name="q5"></textarea></div>
        <div class="question-block"><label>6. Kasih julukan absurd buat semua anggota grup!</label><textarea name="q6"></textarea></div>
        <button type="submit">Kirim Jawaban Absurdku! 🚀</button>
      </div>
      <div class="navigation-buttons">
        <button type="button" id="prevBtn" class="nav-button">⬅ Sebelumnya</button>
        <button type="button" id="nextBtn" class="nav-button">Lanjut ➡</button>
      </div>
    </form>
  </div>

  <script>
    const yesBtn = document.getElementById('yesButton');
    const noBtn = document.getElementById('noButton');
    const intro = document.getElementById('introContainer');
    const form = document.getElementById('formContainer');

    yesBtn.onclick = () => {
      intro.style.display = 'none';
      form.style.display = 'block';
    }

    noBtn.addEventListener('mouseover', () => {
      const container = intro.getBoundingClientRect();
      const btn = noBtn.getBoundingClientRect();
      const x = Math.random() * (window.innerWidth - btn.width - 20);
      const y = Math.random() * (window.innerHeight - btn.height - 20);
      noBtn.style.position = 'absolute';
      noBtn.style.left = x + 'px';
      noBtn.style.top = y + 'px';
    });

    let currentPage = 1;
    const totalPages = 3;
    function showPage(n) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById(`page-${n}`).classList.add('active');
      document.getElementById('prevBtn').style.display = n === 1 ? 'none' : 'inline-block';
      document.getElementById('nextBtn').style.display = n === totalPages ? 'none' : 'inline-block';
    }
    document.getElementById('nextBtn').onclick = () => {
      if (currentPage < totalPages) currentPage++;
      showPage(currentPage);
    };
    document.getElementById('prevBtn').onclick = () => {
      if (currentPage > 1) currentPage--;
      showPage(currentPage);
    };
    showPage(currentPage);
  </script>
</body>
</html>
