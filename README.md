<!DOCTYPE html>
<html>
    <h1>
        <h1 style="font-size:300%;">EA FC 25</h1>
        <img src="https://game4u.co.za/wp-content/uploads/2024/09/fc-25-banner.png" width="1500" height="430">
      
          
        
        <body>

            <div class="container" style="display: flex; align-items: flex-start;">
    <div class="text" style="flex: 1; margin-right: 20px;">
        <h1>Wo kann ich EA FC 25™ spielen?</h1>
        <ul>
            <li>PlayStation® 5</li>
            <li>PlayStation® 4</li>
            <li>Xbox One</li>
            <li>Xbox Series X</li>
            <li>Nintendo Switch™</li>
            <li>PC</li>
        </ul>
    </div>
    <div class="video" style="flex: 1;">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/pBM2xyco_Kg?si=Q-8jKPzcqI0hReFn" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
</div>

          
        <h2>Infos über das spiel</h2>
        <p>Das Spiel EA SPORTS FC™ 25 ist einer Erfindung des Videoherstellers EA™ , das sich rund um Fußball handelt . Das erste spiel ,,FIFA International Soccer´´ kam 1993 raus . Jetzt fragen sich manche bestimmt , warum das Spiel jetzt FIFA und nicht EA SPORTS FC heißt . Das hat einen einfache Grund , denn seit 2024 gehen die beiden Spielersteller FIFA™ und EA SPORTS™ getrennte Wege . Allerdings ist EA SPORTS™ die einzige der beiden Firmen , die der Videospielcommunity weiter ein Fußball-Videospiel liefert.Im September 2024, dem Monat der Veröffentlichung, erreichte das Spiel einen Spitzenwert von 109.977 gleichzeitigen Spielern . Im März 2025 lag dieser Wert bei 91.519 gleichzeitigen Spielern . Bei vielen Videospielern kommt das Spiel sehr gut an jedoch liegt es auch oft in der Kritik durch Spielfehler und schlechte Patches und Updates. Mehr über das spiel erfahren sie in diesem artikel</p>
                
        <img src="https://tiermaker.com/images/media/tierlists-2024/18189549/fc-25-playstyles-tier-list-18011306-1746610206.png" width="800" height="450">  
          
      </iframe>




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
      display: grid;
      gap: 10px;
      justify-content: center;
      align-content: center;
      margin: 2rem auto;
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
    }
    .player-card {
      border: none;
      flex-direction: column;
      position: relative;
    }
    .player-card img {
      width: 80px;
    }
    .chemie-display {
      position: absolute;
      bottom: 5px;
      background: rgba(0,0,0,0.6);
      padding: 2px 6px;
      border-radius: 5px;
      font-size: 12px;
    }
    .bank {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin: 1rem;
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
    </select>
  </div>
  <div class="stats" id="stats">Durchschnittliches Rating: 0 | Chemie: 0</div>
  <div id="pitch" class="pitch"></div>
  <h2>Bank</h2>
  <div class="bank" id="bank"></div>

  <script>
    const formations = {
      "4-3-3": ["GK", "LB", "CB", "CB", "RB", "CM", "CM", "CM", "LW", "ST", "RW"],
      "4-4-2": ["GK", "LB", "CB", "CB", "RB", "LM", "CM", "CM", "RM", "ST", "ST"],
      "3-5-2": ["GK", "CB", "CB", "CB", "LM", "CM", "CAM", "CM", "RM", "ST", "ST"]
    };

    const players = [
      { name: "Mbappé", rating: 91, nation: "France", club: "PSG", pos: "ST", img: "https://cdn.sofifa.net/players/231/747/24_120.png" },
      { name: "Haaland", rating: 91, nation: "Norway", club: "Man City", pos: "ST", img: "https://cdn.sofifa.net/players/239/085/24_120.png" },
      { name: "Messi", rating: 90, nation: "Argentina", club: "Inter Miami", pos: "RW", img: "https://cdn.sofifa.net/players/158/023/24_120.png" },
      { name: "De Bruyne", rating: 91, nation: "Belgium", club: "Man City", pos: "CM", img: "https://cdn.sofifa.net/players/192/985/24_120.png" },
      { name: "Modrić", rating: 87, nation: "Croatia", club: "Real Madrid", pos: "CM", img: "https://cdn.sofifa.net/players/177/003/24_120.png" },
      { name: "Rodri", rating: 89, nation: "Spain", club: "Man City", pos: "CDM", img: "https://cdn.sofifa.net/players/231/866/24_120.png" },
      { name: "Salah", rating: 89, nation: "Egypt", club: "Liverpool", pos: "RW", img: "https://cdn.sofifa.net/players/209/331/24_120.png" },
      { name: "Vinícius Jr.", rating: 89, nation: "Brazil", club: "Real Madrid", pos: "LW", img: "https://cdn.sofifa.net/players/238/794/24_120.png" },
      { name: "Lewandowski", rating: 90, nation: "Poland", club: "Barcelona", pos: "ST", img: "https://cdn.sofifa.net/players/188/545/24_120.png" },
      { name: "Alisson", rating: 89, nation: "Brazil", club: "Liverpool", pos: "GK", img: "https://cdn.sofifa.net/players/212/831/24_120.png" },
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
      layout.forEach(pos => {
        const slot = document.createElement("div");
        slot.className = "slot";
        slot.dataset.pos = pos;
        slot.ondragover = (e) => e.preventDefault();
        slot.ondrop = (e) => {
          const id = e.dataTransfer.getData("text");
          const card = document.getElementById(id);
          if (!Array.from(pitch.querySelectorAll(".player-card")).some(c => c.dataset.name === card.dataset.name)) {
            if (card.dataset.pos === slot.dataset.pos) {
              if (slot.firstChild) bank.appendChild(slot.firstChild);
              slot.innerHTML = "";
              slot.appendChild(card);
              updateStats();
            }
          }
        };
        slot.textContent = pos;
        pitch.appendChild(slot);
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
      card.dataset.pos = p.pos;
      card.innerHTML = `<img src="${p.img}" alt="${p.name}" /><span>${p.name}</span><div class="chemie-display">🔵0</div>`;
      card.ondragstart = (e) => e.dataTransfer.setData("text", card.id);
      card.onclick = () => {
        bank.appendChild(card);
        updateStats();
      };
      bank.appendChild(card);
    }

    function updateStats() {
      const cards = pitch.querySelectorAll(".player-card");
      let total = 0;
      const chemieClub = {};
      const chemieNation = {};

      cards.forEach(card => {
        const rating = parseInt(card.dataset.rating);
        const club = card.dataset.club;
        const nation = card.dataset.nation;
        total += rating;
        chemieClub[club] = (chemieClub[club] || 0) + 1;
        chemieNation[nation] = (chemieNation[nation] || 0) + 1;
      });

      const avg = cards.length ? (total / cards.length).toFixed(1) : 0;
      statsDisplay.textContent = `Durchschnittliches Rating: ${avg}`;

      cards.forEach(card => {
        const club = card.dataset.club;
        const nation = card.dataset.nation;
        let chemie = 0;
        if (chemieClub[club] >= 2) chemie++;
        if (chemieClub[club] >= 4) chemie++;
        if (chemieNation[nation] >= 2) chemie++;
        card.querySelector(".chemie-display").textContent = `🔵${chemie}`;
      });
    }

    formationSelector.addEventListener("change", (e) => {
      createPitch(e.target.value);
    });

    createPitch("4-3-3");
  </script>
</body>
</html>










const players = [
  { name: "Mbappé", rating: 91, nation: "France", club: "PSG", img: "https://cdn.sofifa.net/players/231/747/24_120.png" },
  { name: "Haaland", rating: 91, nation: "Norway", club: "Man City", img: "https://cdn.sofifa.net/players/239/085/24_120.png" },
  { name: "Kane", rating: 89, nation: "England", club: "Bayern", img: "https://cdn.sofifa.net/players/202/126/24_120.png" },
  { name: "Modrić", rating: 87, nation: "Croatia", club: "Real Madrid", img: "https://cdn.sofifa.net/players/177/003/24_120.png" },
  { name: "Bellingham", rating: 86, nation: "England", club: "Real Madrid", img: "https://cdn.sofifa.net/players/247/635/24_120.png" },
  { name: "De Gea", rating: 85, nation: "Spain", club: "Free Agent", img: "https://cdn.sofifa.net/players/193/080/24_120.png" },
  { name: "De Bruyne", rating: 91, nation: "Belgium", club: "Man City", img: "https://cdn.sofifa.net/players/192/985/24_120.png" },
  { name: "Messi", rating: 90, nation: "Argentina", club: "Inter Miami", img: "https://cdn.sofifa.net/players/158/023/24_120.png" },
  { name: "Salah", rating: 89, nation: "Egypt", club: "Liverpool", img: "https://cdn.sofifa.net/players/209/331/24_120.png" },
  { name: "Neymar", rating: 89, nation: "Brazil", club: "Al Hilal", img: "https://cdn.sofifa.net/players/190/871/24_120.png" },
  { name: "Vinícius Jr.", rating: 89, nation: "Brazil", club: "Real Madrid", img: "https://cdn.sofifa.net/players/238/794/24_120.png" },
  { name: "Lewandowski", rating: 90, nation: "Poland", club: "Barcelona", img: "https://cdn.sofifa.net/players/188/545/24_120.png" },
  { name: "Valverde", rating: 88, nation: "Uruguay", club: "Real Madrid", img: "https://cdn.sofifa.net/players/237/692/24_120.png" },
  { name: "Kimmich", rating: 88, nation: "Germany", club: "Bayern", img: "https://cdn.sofifa.net/players/212/622/24_120.png" },
  { name: "Alisson", rating: 89, nation: "Brazil", club: "Liverpool", img: "https://cdn.sofifa.net/players/212/831/24_120.png" },
  { name: "Ter Stegen", rating: 89, nation: "Germany", club: "Barcelona", img: "https://cdn.sofifa.net/players/192/448/24_120.png" },
  { name: "Ederson", rating: 88, nation: "Brazil", club: "Man City", img: "https://cdn.sofifa.net/players/208/330/24_120.png" },
  { name: "van Dijk", rating: 89, nation: "Netherlands", club: "Liverpool", img: "https://cdn.sofifa.net/players/203/376/24_120.png" },
  { name: "Rúben Dias", rating: 88, nation: "Portugal", club: "Man City", img: "https://cdn.sofifa.net/players/239/818/24_120.png" },
  { name: "Courtois", rating: 90, nation: "Belgium", club: "Real Madrid", img: "https://cdn.sofifa.net/players/192/119/24_120.png" },
  { name: "Rodri", rating: 89, nation: "Spain", club: "Man City", img: "https://cdn.sofifa.net/players/231/866/24_120.png" },
  { name: "Son Heung-min", rating: 87, nation: "South Korea", club: "Tottenham", img: "https://cdn.sofifa.net/players/200/104/24_120.png" },
  { name: "Bruno Fernandes", rating: 88, nation: "Portugal", club: "Man Utd", img: "https://cdn.sofifa.net/players/208/722/24_120.png" },
  // Weitere Spieler ergänzen für vollständige Top 100 (z.B. von SoFIFA kopieren)
];

// Der Rest des Codes bleibt gleich


 





