# taksan
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Memnun musunuz?</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
      padding-top: 100px;
      height: 100vh;
      overflow: hidden;
      position: relative;
    }
    h1 {
      margin-bottom: 40px;
    }
    button {
      font-size: 20px;
      padding: 10px 20px;
      margin: 10px;
      cursor: pointer;
      position: absolute;
    }
    #evetBtn {
      left: 40%;
      top: 50%;
    }
    #hayirBtn {
      left: 50%;
      top: 50%;
    }
    #mesaj {
      margin-top: 30px;
      font-size: 24px;
      color: green;
      position: relative;
    }
  </style>
</head>
<body>
  <h1>SERDAR ABİ ARTIK GÖRÜŞELİM </h1>
  <button id="evetBtn">Evet</button>
  <button id="hayirBtn">Hayır</button>
  <div id="mesaj"></div>

  <script>
    const evetBtn = document.getElementById('evetBtn');
    const hayirBtn = document.getElementById('hayirBtn');
    const mesaj = document.getElementById('mesaj');

    function gösterMesajVeBasaDon(metin) {
      mesaj.textContent = metin;
      evetBtn.remove();
      hayirBtn.remove();

      const basaDonBtn = document.createElement('button');
      basaDonBtn.textContent = 'Başa Dön';
      basaDonBtn.style.position = 'static';
      basaDonBtn.onclick = () => location.reload();
      document.body.appendChild(basaDonBtn);
    }

    evetBtn.addEventListener('click', () => {
      gösterMesajVeBasaDon("Doğru seçenek");
    });

    hayirBtn.addEventListener('click', () => {
      gösterMesajVeBasaDon("Başa dön");
    });

    // Hayır butonunun üstüne gelince kaçması için:
    hayirBtn.addEventListener('mouseenter', () => {
      const maxX = window.innerWidth - hayirBtn.offsetWidth;
      const maxY = window.innerHeight - hayirBtn.offsetHeight;

      const randomX = Math.floor(Math.random() * maxX);
      const randomY = Math.floor(Math.random() * maxY);

      hayirBtn.style.left = `${randomX}px`;
      hayirBtn.style.top = `${randomY}px`;
    });
  </script>
</body>
</html>
