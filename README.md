# Oi-Musang2
SINI MAIN
<!DOCTYPE html>
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
    }
    header {
      text-align: center;
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
    p {
      font-size: 16px;
      color: #444;
    }
    .question-block {
      margin-bottom: 25px;
    }
    label {
      display: block;
      font-weight: bold;
      margin-bottom: 8px;
      color: #c2410c;
    }
    textarea {
      width: 100%;
      padding: 10px;
      border-radius: 12px;
      border: 1px solid #ccc;
      font-size: 15px;
      resize: vertical;
      font-family: 'Comic Neue', cursive;
    }
    .navigation-buttons {
      display: flex;
      justify-content: space-between;
      margin-top: 25px;
    }
    .nav-button {
      padding: 12px 24px;
      font-size: 15px;
      font-weight: bold;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      background-color: #fde68a;
      color: #78350f;
    }
    button[type="submit"] {
      display: block;
      width: 100%;
      margin-top: 30px;
      padding: 15px;
      font-size: 17px;
      font-weight: bold;
      color: white;
      background: linear-gradient(to right, #fbbf24, #f59e0b);
      border: none;
      border-radius: 20px;
      cursor: pointer;
    }
    .page {
      display: none;
    }
    .page.active {
      display: block;
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <img src="https://media.tenor.com/HL9i_cy3cvUAAAAi/funny-animal.gif" alt="Funny Animal" />
      <h1>Welcome ke Zona Kocak Musang! 🐾</h1>
      <p>Jawab seabsurd dan sejujurnya mungkin biar makin seru dan deket!</p>
    </header>

    <form action="https://formspree.io/f/xanjdrpq" method="POST">
      <div id="page-1" class="page active">
        <div class="question-block"><label>1. Kalau kamu jadi hewan 1 hari, kamu mau jadi apa dan ngapain aja?</label><textarea name="q1"></textarea></div>
        <div class="question-block"><label>2. Siapa yang paling mungkin jadi presiden negara musang, dan kenapa?</label><textarea name="q2"></textarea></div>
        <div class="question-block"><label>3. Kalau kita punya reality show, judulnya apa?</label><textarea name="q3"></textarea></div>
        <div class="question-block"><label>4. Momen paling absurd yang pernah terjadi di grup ini?</label><textarea name="q4"></textarea></div>
      </div>

      <div id="page-2" class="page">
        <div class="question-block"><label>5. Kalau cuma bisa komunikasi lewat emot, emot apa yang kamu pilih?</label><textarea name="q5"></textarea></div>
        <div class="question-block"><label>6. Siapa yang paling mungkin jadi alien yang nyamar selama ini?</label><textarea name="q6"></textarea></div>
        <div class="question-block"><label>7. Kalau kita liburan bareng, siapa yang bakal nyasar duluan?</label><textarea name="q7"></textarea></div>
        <div class="question-block"><label>8. Zombie apocalypse: siapa yang survive terakhir?</label><textarea name="q8"></textarea></div>
      </div>

      <div id="page-3" class="page">
        <div class="question-block"><label>9. Kalau jadi karakter kartun, kamu jadi siapa?</label><textarea name="q9"></textarea></div>
        <div class="question-block"><label>10. Pernah pura-pura sibuk biar gak bales chat grup? Ngaku 😆</label><textarea name="q10"></textarea></div>
        <div class="question-block"><label>11. Siapa paling cepet kirim stiker pas lagi serius-seriusnya?</label><textarea name="q11"></textarea></div>
        <div class="question-block"><label>12. Kalau kita bikin band, kamu bagian apa? Nama bandnya?</label><textarea name="q12"></textarea></div>
      </div>

      <div id="page-4" class="page">
        <div class="question-block"><label>13. Siapa yang cocok jadi villain di film superhero?</label><textarea name="q13"></textarea></div>
        <div class="question-block"><label>14. Kalau semua jadi makanan, kamu jadi makanan apa?</label><textarea name="q14"></textarea></div>
        <div class="question-block"><label>15. Momen paling ngakak bareng?</label><textarea name="q15"></textarea></div>
        <div class="question-block"><label>16. Hal konyol apa yang pengen kita lakuin bareng?</label><textarea name="q16"></textarea></div>
        <div class="question-block"><label>17. Pernah kejebak auto-correct dan malu sendiri?</label><textarea name="q17"></textarea></div>
        <div class="question-block"><label>18. Kasih julukan absurd buat semua anggota grup!</label><textarea name="q18"></textarea></div>

        <button type="submit">Kirim Jawaban Absurdku! 🚀</button>
      </div>

      <div class="navigation-buttons">
        <button type="button" id="prevBtn" class="nav-button">⬅ Sebelumnya</button>
        <button type="button" id="nextBtn" class="nav-button">Lanjut ➡</button>
      </div>
    </form>
  </div>

  <script>
    let currentPage = 1;
    const totalPages = 4;
    function showPage(num) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById(`page-${num}`).classList.add('active');
      document.getElementById('prevBtn').style.display = num === 1 ? 'none' : 'inline-block';
      document.getElementById('nextBtn').style.display = num === totalPages ? 'none' : 'inline-block';
    }
    document.getElementById('nextBtn').addEventListener('click', () => {
      if (currentPage < totalPages) {
        currentPage++;
        showPage(currentPage);
      }
    });
    document.getElementById('prevBtn').addEventListener('click', () => {
      if (currentPage > 1) {
        currentPage--;
        showPage(currentPage);
      }
    });
    showPage(currentPage);
  </script>
</body>
</html>
