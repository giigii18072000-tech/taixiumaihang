<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tài Xỉu Mai Hằng</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: Arial, sans-serif;
      min-height: 100vh;
      background: linear-gradient(180deg, #44251e 0%, #211513 60%, #100c0d 100%);
      color: #fff;
      padding: 18px;
    }
    .game {
      width: 100%;
      max-width: 1280px;
      margin: 0 auto;
      border-radius: 28px;
      padding: 22px;
      background: rgba(0,0,0,0.30);
      box-shadow: 0 18px 50px rgba(0,0,0,0.45);
      border: 1px solid rgba(255,255,255,0.08);
    }
    .site-name {
      text-align: center;
      font-size: 34px;
      font-weight: 900;
      color: #ffe6a6;
      margin-bottom: 16px;
      text-transform: uppercase;
      letter-spacing: 2px;
      text-shadow: 0 4px 18px rgba(0,0,0,0.45);
    }
    .top-info {
      display: flex;
      justify-content: center;
      gap: 12px;
      margin-bottom: 18px;
      flex-wrap: wrap;
    }
    .pill {
      background: rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 999px;
      padding: 10px 16px;
      font-weight: 700;
    }
    .top-photo {
      width: 100%;
      max-width: 320px;
      margin: 0 auto 18px;
      border-radius: 24px;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.10);
      box-shadow: 0 14px 30px rgba(0,0,0,0.28);
      background: rgba(255,255,255,0.06);
    }
    .top-photo img {
      width: 100%;
      display: block;
      object-fit: cover;
    }
    .top-gallery {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 16px;
      margin: 0 auto 18px;
      max-width: 980px;
    }
    .top-gallery a {
      display: block;
      width: 100%;
      aspect-ratio: 1 / 1;
      border-radius: 20px;
      overflow: hidden;
      border: 1px solid rgba(255,255,255,0.10);
      box-shadow: 0 14px 30px rgba(0,0,0,0.28);
      background: rgba(255,255,255,0.06);
    }
    .top-gallery img {
      width: 100%;
      height: 100%;
      display: block;
      object-fit: cover;
    }
    .arena {
      display: grid;
      grid-template-columns: 1fr 380px;
      gap: 18px;
      align-items: start;
    }
    .side-stack {
      display: grid;
      gap: 16px;
    }
    .decor-card {
      position: relative;
      min-height: 220px;
      border-radius: 22px;
      overflow: hidden;
      background: linear-gradient(135deg, rgba(120,20,20,0.95), rgba(40,10,10,0.95));
      border: 1px solid rgba(255,255,255,0.08);
      box-shadow: 0 12px 30px rgba(0,0,0,0.25);
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .decor-card.alt {
      background: linear-gradient(135deg, rgba(20,60,120,0.95), rgba(10,20,50,0.95));
    }
    .decor-inner {
      text-align: center;
      padding: 20px;
    }
    .decor-title {
      font-size: 32px;
      font-weight: 900;
      color: #fff3c6;
      letter-spacing: 2px;
      margin-bottom: 8px;
    }
    .decor-sub {
      font-size: 15px;
      color: rgba(255,255,255,0.85);
      line-height: 1.6;
    }
    .angry {
      position: absolute;
      font-size: 28px;
      animation: floatAngry 5s ease-in-out infinite;
      filter: drop-shadow(0 4px 8px rgba(0,0,0,0.35));
      user-select: none;
      pointer-events: none;
    }
    .a1 { top: 8px; left: 10px; }
    .a2 { top: 12px; right: 12px; animation-delay: -1s; }
    .a3 { bottom: 10px; left: 14px; animation-delay: -2s; }
    .a4 { bottom: 10px; right: 14px; animation-delay: -3s; }
    @keyframes floatAngry {
      0% { transform: translate(0,0) rotate(0deg); }
      25% { transform: translate(6px,-8px) rotate(6deg); }
      50% { transform: translate(-5px,6px) rotate(-5deg); }
      75% { transform: translate(7px,4px) rotate(4deg); }
      100% { transform: translate(0,0) rotate(0deg); }
    }
    .table-wrap {
      background: linear-gradient(180deg, rgba(88,20,20,0.95), rgba(55,10,10,0.95));
      border-radius: 32px;
      padding: 18px;
      box-shadow: inset 0 0 0 3px rgba(255,215,120,0.18), inset 0 0 40px rgba(0,0,0,0.45);
    }

    .table-image-wrap {
      position: relative;
      width: min(100%, 760px);
      margin: 0 auto;
      border-radius: 28px;
      overflow: hidden;
      box-shadow: 0 18px 40px rgba(0,0,0,0.28);
      border: 1px solid rgba(255,255,255,0.1);
      background: rgba(255,255,255,0.04);
    }

    .table-image-wrap img {
      width: 100%;
      display: block;
      object-fit: cover;
    }

    .table-overlay {
      position: absolute;
      inset: 0;
      pointer-events: none;
    }

    .choice-hotspot {
      position: absolute;
      pointer-events: auto;
      cursor: pointer;
      border-radius: 22px;
      transition: 0.2s ease;
      border: 2px solid transparent;
      background: rgba(255,255,255,0.02);
    }

    .choice-hotspot:hover {
      background: rgba(255,255,255,0.08);
      transform: scale(1.02);
    }

    .choice-hotspot.active {
      border-color: #ffe6a6;
      box-shadow: 0 0 0 4px rgba(255,230,166,0.22);
      background: rgba(255,255,255,0.08);
    }

    .choice-hotspot.tai-hotspot {
      left: 14%;
      top: 54%;
      width: 25%;
      height: 27%;
    }

    .choice-hotspot.xiu-hotspot {
      right: 13%;
      top: 54%;
      width: 25%;
      height: 27%;
    }

    .table-bet-label {
      position: absolute;
      min-width: 90px;
      padding: 10px 14px;
      border-radius: 14px;
      text-align: center;
      font-size: 24px;
      font-weight: 900;
      color: #fff8d8;
      background: rgba(0,0,0,0.35);
      backdrop-filter: blur(6px);
      border: 1px solid rgba(255,255,255,0.12);
      text-shadow: 0 2px 10px rgba(0,0,0,0.4);
    }

    .table-bet-label.tai-label {
      left: 20%;
      top: 68%;
    }

    .table-bet-label.xiu-label {
      right: 19%;
      top: 68%;
    }

    .hero-banner {
      border-radius: 22px;
      margin-bottom: 16px;
      border: 1px solid rgba(255,255,255,0.08);
      background: linear-gradient(135deg, #7d1212, #2d0e0e);
      padding: 22px;
      text-align: center;
      box-shadow: inset 0 0 0 1px rgba(255,255,255,0.06);
    }
    .hero-banner h2 {
      font-size: 28px;
      color: #ffe6a6;
      margin-bottom: 8px;
    }
    .hero-banner p {
      color: rgba(255,255,255,0.84);
      line-height: 1.6;
    }
    .table {
      display: none;
    }

    .pip {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: transparent;
      align-self: center;
      justify-self: center;
    }
    .pip.on { background: #16316b; }
    .pip.red { background: #c01a1a; }
    .panel {
      background: rgba(255,255,255,0.07);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 24px;
      padding: 18px;
      display: grid;
      gap: 14px;
      align-content: start;
    }
    .panel h3 { color: #ffe099; font-size: 24px; }
    .stats {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }
    .card {
      background: rgba(255,255,255,0.08);
      border-radius: 18px;
      padding: 14px;
      border: 1px solid rgba(255,255,255,0.08);
    }
    .label { color: rgba(255,255,255,0.7); font-size: 13px; margin-bottom: 8px; }
    .value { font-size: 28px; font-weight: 800; }
    .bet-list {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
    }
    .bet-option, button.main, button.alt {
      border: none;
      border-radius: 12px;
      padding: 10px 14px;
      color: #fff;
      font-weight: 800;
      cursor: pointer;
      min-width: 70px;
    }
    .bet-option { background: linear-gradient(180deg, #d0d0d0, #9d9d9d); }
    .actions {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }
    button.main { background: linear-gradient(180deg, #6e6e6e, #434343); }
    button.alt { background: linear-gradient(180deg, #434343, #212121); }
    .full-btn {
      width: 100%;
      padding: 14px;
      border-radius: 14px;
      border: none;
      background: linear-gradient(180deg, #e1aa27, #b57b07);
      color: #2d1800;
      font-size: 17px;
      font-weight: 800;
      cursor: pointer;
    }
    .msg {
      min-height: 72px;
      background: rgba(255,255,255,0.08);
      border-radius: 16px;
      padding: 14px;
      line-height: 1.6;
      color: #fff4cf;
    }
    .hidden { display: none; }
    .avatar-panel {
      background: rgba(255,255,255,0.08);
      border-radius: 18px;
      padding: 14px;
      border: 1px solid rgba(255,255,255,0.08);
      display: grid;
      gap: 12px;
    }
    .avatar-figure {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      padding: 12px 0 6px;
    }
    .bird {
      font-size: 34px;
      transition: 0.2s ease;
      cursor: pointer;
    }
    .head {
      width: 64px;
      height: 64px;
      border-radius: 50%;
      background: linear-gradient(180deg, #ffe6bf, #e0b48a);
      border: 3px solid rgba(255,255,255,0.6);
      box-shadow: 0 4px 10px rgba(0,0,0,0.25);
    }
    .arms, .legs {
      display: flex;
      justify-content: center;
      gap: 14px;
      width: 100%;
    }
    .body {
      width: 60px;
      height: 90px;
      border-radius: 18px;
      background: linear-gradient(180deg, #7ec7ff, #4e8dd2);
    }
    .limb {
      width: 20px;
      height: 70px;
      border-radius: 999px;
      background: linear-gradient(180deg, #ffe0c1, #d6a27b);
      transition: 0.2s ease;
      cursor: pointer;
    }
    .limb.lost, .bird.lost {
      opacity: 0.16;
      filter: grayscale(1);
      transform: scale(0.92);
    }
    .collateral-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }
    @media (max-width: 1100px) {
      .arena { grid-template-columns: 1fr; }
    }
    @media (max-width: 820px) {
      .top-gallery { grid-template-columns: 1fr; }
      .stats, .actions, .collateral-grid { grid-template-columns: 1fr; }
      .table-image-wrap { border-radius: 20px; }
      .table-bet-label {
        min-width: 72px;
        font-size: 18px;
        padding: 8px 10px;
      }
    }
  </style>
</head>
<body>
  <div class="game">
    <div class="site-name">Tài Xỉu Mai Hằng</div>
    <div class="top-gallery">
      <a href="https://imgbb.com/" target="_blank">
        <img src="https://i.ibb.co/jsfn13M/nh-ch-p-m-n-h-nh-2026-03-12-010617.png" alt="Ảnh 1">
      </a>
      <a href="https://imgbb.com/" target="_blank">
        <img src="https://i.ibb.co/C3fnfvCK/nh-ch-p-m-n-h-nh-2026-03-12-010635.png" alt="Ảnh 2">
      </a>
      <a href="https://imgbb.com/" target="_blank">
        <img src="https://i.ibb.co/KjPJGHD2/nh-ch-p-m-n-h-nh-2026-03-14-001026.png" alt="Ảnh 3">
      </a>
    </div>
    <div class="top-info">
      <div class="pill">Số dư: <span id="balance">10000</span></div>
      <div class="pill">Nợ hiện tại: <span id="debt">0</span></div>
      <div class="pill">Mức cược: <span id="betDisplay">1000</span></div>
    </div>

    <div class="arena">
      <div class="table-wrap">
        <div class="hero-banner">
          <h2>Tài Xỉu Mai Hằng</h2>
          <p>Giao diện đã được rút gọn, bỏ các bảng trang trí hai bên để tập trung vào bàn chơi và điều khiển.</p>
        </div>

        <div class="table-image-wrap">
       <a href="https://ibb.co/YBdrfMyW"><img src="https://i.ibb.co/fdNcr5nS/unnamed.jpg" alt="unnamed" border="0"></a>
          <div class="table-overlay">
            <div class="choice-hotspot tai-hotspot" id="taiZone" onclick="selectChoice('Tài')"></div>
            <div class="choice-hotspot xiu-hotspot" id="xiuZone" onclick="selectChoice('Xỉu')"></div>
            <div class="table-bet-label tai-label" id="taiBet">0</div>
            <div class="table-bet-label xiu-label" id="xiuBet">0</div>
          </div>
        </div>
      </div>

      <div class="panel">
          <h3>Bảng điều khiển</h3>

          <div class="stats">
            <div class="card">
              <div class="label">Đã chọn</div>
              <div class="value" id="selectedChoice">Chưa chọn</div>
            </div>
            <div class="card">
              <div class="label">Tổng xúc xắc</div>
              <div class="value" id="sumDice">?</div>
            </div>
          </div>

          <div>
            <div class="label">Chọn nhanh tiền cược</div>
            <div class="bet-list">
              <button class="bet-option" onclick="setBet(1000)">1K</button>
              <button class="bet-option" onclick="setBet(5000)">5K</button>
              <button class="bet-option" onclick="setBet(10000)">10K</button>
              <button class="bet-option" onclick="setBet(15000)">15K</button>
              <button class="bet-option" onclick="setBet(20000)">20K</button>
              <button class="bet-option" onclick="setBet(30000)">30K</button>
            </div>
          </div>

          <div>
            <div class="label">Thêm số tiền cược</div>
            <div class="actions">
              <input id="customBet" type="number" min="1000" step="1000" placeholder="Nhập tiền cược" style="padding:14px;border:none;border-radius:14px;font-size:16px;">
              <button class="main" onclick="applyCustomBet()">Áp dụng</button>
            </div>
          </div>

          <div class="actions">
            <button class="main" onclick="playGame()">Bet</button>
            <button class="alt" onclick="resetRound()">Cancel</button>
          </div>

          <button class="full-btn hidden" id="loanBtn" onclick="borrowMoney()">Vay nợ +10000</button>

          <div class="avatar-panel">
            <div class="label">Tài sản thế vay</div>
            <div class="avatar-figure">
              <div class="bird" id="birdPart" onclick="pledgeSpecific('birdPart')">🐦</div>
              <div class="head"></div>
              <div class="arms">
                <div class="limb" id="leftArm" onclick="pledgeSpecific('leftArm')"></div>
                <div class="body"></div>
                <div class="limb" id="rightArm" onclick="pledgeSpecific('rightArm')"></div>
              </div>
              <div class="legs">
                <div class="limb" id="leftLeg" onclick="pledgeSpecific('leftLeg')"></div>
                <div class="limb" id="rightLeg" onclick="pledgeSpecific('rightLeg')"></div>
              </div>
            </div>
            <div class="collateral-grid">
              <button class="main" onclick="pledgeSpecific('leftArm')">Tay trái 10000</button>
              <button class="main" onclick="pledgeSpecific('rightArm')">Tay phải 10000</button>
              <button class="main" onclick="pledgeSpecific('leftLeg')">Chân trái 10000</button>
              <button class="main" onclick="pledgeSpecific('rightLeg')">Chân phải 10000</button>
              <button class="main" onclick="pledgeSpecific('birdPart')">Con chim 10000</button>
              <button class="alt" onclick="restoreLastPledged()">Chuộc lại</button>
            </div>
          </div>

          <div class="msg" id="messageBox">Chọn Tài hoặc Xỉu, đặt cược rồi bấm Bet.</div>
        </div>
      </div>
    </div>
  </div>

  <script>
    let balance = 10000;
    let debt = 0;
    let currentBet = 1000;
    let selectedChoice = '';
    const pledgeOrder = [];

    const dicePatterns = {
      1: [0,0,0,0,1,0,0,0,0],
      2: [1,0,0,0,0,0,0,0,1],
      3: [1,0,0,0,1,0,0,0,1],
      4: [1,0,1,0,0,0,1,0,1],
      5: [1,0,1,0,1,0,1,0,1],
      6: [1,0,1,1,0,1,1,0,1]
    };

    function renderDice(elId, value, useRed = false) {
      const el = document.getElementById(elId);
      el.innerHTML = '';
      dicePatterns[value].forEach(on => {
        const pip = document.createElement('span');
        pip.className = 'pip' + (on ? ' on' : '') + (useRed && on ? ' red' : '');
        el.appendChild(pip);
      });
    }

    function rollInitialDice() {
      renderDice('dice1', 5);
      renderDice('dice2', 4, true);
      renderDice('dice3', 2);
    }

    function updateUI() {
      document.getElementById('balance').textContent = balance;
      document.getElementById('debt').textContent = debt;
      document.getElementById('betDisplay').textContent = currentBet;
      document.getElementById('selectedChoice').textContent = selectedChoice || 'Chưa chọn';
      document.getElementById('taiBet').textContent = selectedChoice === 'Tài' ? currentBet : 0;
      document.getElementById('xiuBet').textContent = selectedChoice === 'Xỉu' ? currentBet : 0;
      document.getElementById('taiZone').classList.toggle('active', selectedChoice === 'Tài');
      document.getElementById('xiuZone').classList.toggle('active', selectedChoice === 'Xỉu');
      document.getElementById('loanBtn').classList.toggle('hidden', balance >= currentBet);
    }

    function setBet(amount) {
      currentBet = amount;
      updateUI();
    }

    function applyCustomBet() {
      const val = parseInt(document.getElementById('customBet').value, 10);
      if (!val || val < 1000) {
        showMessage('Vui lòng nhập tiền cược từ 1000 trở lên.');
        return;
      }
      currentBet = val;
      updateUI();
      showMessage('Đã cập nhật tiền cược: ' + currentBet);
    }

    function selectChoice(choice) {
      selectedChoice = choice;
      updateUI();
      showMessage('Bạn đã chọn ' + choice + '.');
    }

    function showMessage(msg) {
      document.getElementById('messageBox').textContent = msg;
    }

    function pledgeSpecific(partId) {
      const el = document.getElementById(partId);
      if (!el || el.classList.contains('lost')) {
        showMessage('Bộ phận này đã được thế rồi.');
        return;
      }
      el.classList.add('lost');
      pledgeOrder.push(partId);
      debt += 10000;
      balance += 10000;
      updateUI();
      showMessage('Đã thế bộ phận và nhận 10000.');
    }

    function restoreLastPledged() {
      if (pledgeOrder.length === 0) {
        showMessage('Chưa có bộ phận nào đang thế.');
        return;
      }
      if (balance < 10000) {
        showMessage('Bạn cần ít nhất 10000 để chuộc lại.');
        return;
      }
      const last = pledgeOrder.pop();
      const el = document.getElementById(last);
      if (el) el.classList.remove('lost');
      balance -= 10000;
      debt = Math.max(0, debt - 10000);
      updateUI();
      showMessage('Đã chuộc lại 1 bộ phận.');
    }

    function borrowMoney() {
      debt += 10000;
      balance += 10000;
      updateUI();
      showMessage('Bạn đã vay thêm 10000 để tiếp tục chơi.');
    }

    function randomDice() {
      return Math.floor(Math.random() * 6) + 1;
    }

    function playGame() {
      if (!selectedChoice) {
        showMessage('Bạn cần chọn Tài hoặc Xỉu trước khi cược.');
        return;
      }
      if (balance < currentBet) {
        showMessage('Không đủ tiền cược. Bấm vay nợ để tiếp tục.');
        updateUI();
        return;
      }
      balance -= currentBet;
      const d1 = randomDice();
      const d2 = randomDice();
      const d3 = randomDice();
      const sum = d1 + d2 + d3;
      const result = sum >= 11 ? 'Tài' : 'Xỉu';
      renderDice('dice1', d1);
      renderDice('dice2', d2, true);
      renderDice('dice3', d3);
      document.getElementById('sumDice').textContent = sum;
      if (selectedChoice === result) {
        balance += currentBet * 2;
        showMessage('Bạn đã cược thắng. Kết quả là ' + result + ' (' + sum + ').');
      } else {
        showMessage('Bạn cược chưa trúng. Kết quả là ' + result + ' (' + sum + ').');
      }
      updateUI();
    }

    function resetRound() {
      selectedChoice = '';
      document.getElementById('sumDice').textContent = '?';
      document.getElementById('customBet').value = '';
      rollInitialDice();
      updateUI();
      showMessage('Đã huỷ lượt chọn.');
    }

    rollInitialDice();
    updateUI();
  </script>
</body>
</html>
