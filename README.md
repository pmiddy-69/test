<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>EAFC Squad Builder</title>
  <style>
    body {
      font-family: sans-serif;
      margin: 0;
      padding: 0;
      background-color: #0f172a;
      color: white;
    }
    .formation-selector {
      margin: 1rem;
    }
    .stats {
      text-align: center;
      font-size: 1.2rem;
      margin: 1rem;
    }
    .pitch {
      display: flex;
      flex-direction: column;
      gap: 10px;
      align-items: center;
      margin: 2rem auto;
    }
    .line {
      display: flex;
      justify-content: center;
      gap: 10px;
    }
    .slot, .player-card {
      width: 100px;
      height: 140px;
      background-color: #1e293b;
      display: flex;
      justify-content: center;
      align-items: center;
      border-radius: 10px;
      cursor: pointer;
      border: 2px dashed white;
      color: white;
      font-weight: bold;
      position: relative;
      text-align: center;
    }
    .slot-text {
      position: absolute;
      bottom: 5px;
      font-size: 12px;
      color: #94a3b8;
      pointer-events: none;
    }
    .player-card {
      border: none;
      flex-direction: column;
      cursor: grab;
    }
    .player-card img {
      width: 80px;
      border-radius: 5px;
      margin-bottom: 5px;
    }
    .chemie-display {
      position: absolute;
      bottom: 5px;
      background: rgba(0,0,0,0.6);
      padding: 2px 6px;
      border-radius: 5px;
      font-size: 12px;
      user-select: none;
    }
    .bank {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin: 1rem;
      justify-content: center;
    }
  </style>
</head>
<body>
  <div class="formation-selector">
    <label for="formation">Formation wählen:</label>
    <select id="formation">
      <option value="4-3-3">4-3-3</option>
      <option value="4-4-2">4-4-2</option>
      <option value="3-5-2">3-5-2</option>
      <option value="4-2-3-1">4-2-3-1</option>
    </select>
  </div>
  <div class="stats" id="stats">Durchschnittliches Rating: 0 | Chemie: 0</div>
  <div id="pitch" class="pitch"></div>
  <h2>Bank</h2>
  <div class="bank" id="bank"></div>

  <script>
    const formations = {
      "4-3-3": [["GK"], ["LB", "CB", "CB", "RB"], ["CM", "CM", "CM"], ["LW", "ST", "RW"]],
      "4-4-2": [["GK"], ["LB", "CB", "CB", "RB"], ["LM", "CM", "CM", "RM"], ["ST", "ST"]],
      "3-5-2": [["GK"], ["CB", "CB", "CB"], ["LM", "CM", "CAM", "CM", "RM"], ["ST", "ST"]],
      "4-2-3-1": [["GK"], ["LB", "CB", "CB", "RB"], ["CDM", "CDM"], ["CAM", "LAM", "RAM"], ["ST"]]
    };

    const players = [
      { name: "Mbappé", rating: 91, nation: "France", club: "PSG", liga: "Ligue 1", pos: ["ST", "LW"], img: "https://cdn.sofifa.net/players/231/747/24_120.png" },
      { name: "Haaland", rating: 91, nation: "Norway", club: "Man City", liga: "Premier League", pos: ["ST"], img: "https://cdn.sofifa.net/players/239/085/24_120.png" },
      { name: "Messi", rating: 88, nation: "Argentina", club: "Inter Miami", liga: "MLS", pos: ["RW", "CAM", "LAM", "RAM"], img: "https://cdn.sofifa.net/players/158/023/24_120.png" },
      { name: "De Bruyne", rating: 90, nation: "Belgium", club: "Man City", liga: "Premier League", pos: ["CM", "CAM"], img: "https://cdn.sofifa.net/players/192/985/24_120.png" },
      { name: "Modrić", rating: 87, nation: "Croatia", club: "Real Madrid", liga: "La Liga", pos: ["CM", "CDM"], img: "https://cdn.sofifa.net/players/177/003/24_120.png" },
      { name: "Rodri", rating: 91, nation: "Spain", club: "Man City", liga: "Premier League", pos: ["CDM", "CM"], img: "https://cdn.sofifa.net/players/231/866/24_120.png" },
      { name: "Salah", rating: 89, nation: "Egypt", club: "Liverpool", liga: "Premier League", pos: ["RW", "RM"], img: "https://cdn.sofifa.net/players/209/331/24_120.png" },
      { name: "Vinícius Jr.", rating: 91, nation: "Brazil", club: "Real Madrid", liga: "La Liga", pos: ["LW", "LM"], img: "https://cdn.sofifa.net/players/238/794/24_120.png" },
      { name: "Lewandowski", rating: 90, nation: "Poland", club: "Barcelona", liga: "La Liga", pos: ["ST"], img: "https://cdn.sofifa.net/players/188/545/24_120.png" },
      { name: "Alisson", rating: 89, nation: "Brazil", club: "Liverpool", liga: "Premier League", pos: ["GK"], img: "https://cdn.sofifa.net/players/212/831/24_120.png" },
      { name: "Neymar", rating: 88, nation: "Brazil", club: "Al Hilal", liga: "Saudi Pro League", pos: ["LW", "CAM"], img: "https://cdn.sofifa.net/players/190/871/24_120.png" },
      { name: "Kimmich", rating: 88, nation: "Germany", club: "Bayern Munich", liga: "Bundesliga", pos: ["CDM", "CM", "RB"], img: "https://cdn.sofifa.net/players/212/622/24_120.png" },
      { name: "Kane", rating: 90, nation: "England", club: "Bayern Munich", liga: "Bundesliga", pos: ["ST"], img: "https://cdn.sofifa.net/players/202/126/24_120.png" },
      { name: "Ter Stegen", rating: 89, nation: "Germany", club: "Barcelona", liga: "La Liga", pos: ["GK"], img: "https://cdn.sofifa.net/players/192/448/24_120.png" },
      { name: "Bellingham", rating: 90, nation: "England", club: "Real Madrid", liga: "La Liga", pos: ["CM", "CAM"], img: "https://cdn.sofifa.net/players/252/371/25_120.png" },
      { name: "Middy gel 7", rating: 69, nation: "Germany", club: "Real Madrid", liga: "La Liga", pos: ["GK", "LB", "CB", "RB", "CDM", "CM", "CAM", "LM", "RM", "LW", "RW", "ST"], img: "https://i.postimg.cc/hvMbnbp6/Screenshot-2025-04-09-113744.png" },
      { name: "Fredi", rating: 69, nation: "Germany", club: "Bayern Munich", liga: "Bundesliga", pos: ["GK", "LB", "CB", "RB", "CDM", "CM", "CAM", "LM", "RM", "LW", "RW", "ST"], img: "https://i.postimg.cc/pXRR1YNx/IMG-0256.jpg" },
      { name: "John Pork", rating: 99, nation: "Germany", club: "Bayern Munich", liga: "Bundesliga", pos: ["GK", "LB", "CB", "RB", "CDM", "CM", "CAM", "LM", "RM", "LW", "RW", "ST"], img: "https://i.imgur.com/w9kWovj.png" },
      { name: "Thorsten abi", rating: 99, nation: "Germany", club: "Bayern Munich", liga: "Bundesliga", pos: ["GK", "LB", "CB", "RB", "CDM", "CM", "CAM", "LM", "RM", "LW", "RW", "ST"], img: "https://i.postimg.cc/Sxkg6NvN/Screenshot-2025-06-06-082011.png" }
      ];

    const pitch = document.getElementById("pitch");
    const bank = document.getElementById("bank");
    const formationSelector = document.getElementById("formation");
    const statsDisplay = document.getElementById("stats");

    function createPitch(formation) {
      pitch.innerHTML = "";
      bank.innerHTML = "";
      players.forEach((p, index) => addPlayerToBank(p, index));

      const layout = formations[formation];
      layout.forEach(row => {
        const line = document.createElement("div");
        line.className = "line";
        row.forEach(pos => {
          const slot = document.createElement("div");
          slot.className = "slot";
          slot.dataset.pos = pos;

          const posLabel = document.createElement("div");
          posLabel.className = "slot-text";
          posLabel.textContent = pos;
          slot.appendChild(posLabel);

          slot.ondragover = (e) => e.preventDefault();
          slot.ondrop = (e) => {
            e.preventDefault();
            const id = e.dataTransfer.getData("text");
            const card = document.getElementById(id);
            if (!Array.from(pitch.querySelectorAll(".player-card")).some(c => c.dataset.name === card.dataset.name)) {
              const positions = JSON.parse(card.dataset.pos);
              if (positions.includes(slot.dataset.pos)) {
                if (slot.querySelector(".player-card")) bank.appendChild(slot.querySelector(".player-card"));
                slot.appendChild(card);
                updateStats();
              }
            }
          };
          slot.onclick = () => filterPlayersForPosition(pos);
          line.appendChild(slot);
        });
        pitch.appendChild(line);
      });
    }

    function addPlayerToBank(p, index) {
      const card = document.createElement("div");
      card.className = "player-card";
      card.draggable = true;
      card.id = `player-${index}`;
      card.dataset.name = p.name;
      card.dataset.rating = p.rating;
      card.dataset.club = p.club;
      card.dataset.nation = p.nation;
      card.dataset.liga = p.liga;
      card.dataset.pos = JSON.stringify(p.pos);
      card.innerHTML = `<img src="${p.img}" alt="${p.name}" /><span>${p.name}</span><div class="chemie-display">🔵0</div>`;
      card.ondragstart = (e) => e.dataTransfer.setData("text", card.id);
      card.onclick = () => {
        bank.appendChild(card);
        showAllPlayers();
        updateStats();
      };
      bank.appendChild(card);
    }

    function updateStats() {
      const cards = pitch.querySelectorAll(".player-card");
      let totalRating = 0;
      const chemieClub = {};
      const chemieNation = {};
      const chemieLiga = {};

      cards.forEach(card => {
        const rating = parseInt(card.dataset.rating);
        const club = card.dataset.club;
        const nation = card.dataset.nation;
        const liga = card.dataset.liga;
        totalRating += rating;

        chemieClub[club] = (chemieClub[club] || 0) + 1;
        chemieNation[nation] = (chemieNation[nation] || 0) + 1;
        chemieLiga[liga] = (chemieLiga[liga] || 0) + 1;
      });

      const avgRating = cards.length ? (totalRating / cards.length).toFixed(1) : 0;

      cards.forEach(card => {
        const club = card.dataset.club;
        const nation = card.dataset.nation;
        const liga = card.dataset.liga;
        let chemie = 0;
        if (chemieClub[club] >= 2) chemie++;
        if (chemieClub[club] >= 4) chemie++;
        if (chemieNation[nation] >= 2) chemie++;
        if (chemieLiga[liga] >= 2) chemie++;
        card.querySelector(".chemie-display").textContent = `🔵${chemie}`;
      });

      statsDisplay.textContent = `Durchschnittliches Rating: ${avgRating} | Spieler: ${cards.length}`;
    }

    function filterPlayersForPosition(pos) {
      Array.from(bank.children).forEach(card => {
        const positions = JSON.parse(card.dataset.pos);
        if (positions.includes(pos)) {
          card.style.opacity = "1";
          card.style.border = "2px solid limegreen";
        } else {
          card.style.opacity = "0.3";
          card.style.border = "2px solid transparent";
        }
      });
    }

    function showAllPlayers() {
      Array.from(bank.children).forEach(card => {
        card.style.opacity = "1";
        card.style.border = "2px solid transparent";
      });
    }

    formationSelector.addEventListener("change", (e) => {
      createPitch(e.target.value);
    });

    createPitch("4-3-3");
  </script>
</body>
</html>






