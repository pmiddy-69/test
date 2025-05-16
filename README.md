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
  <meta charset="UTF-8">
  <title>EAFC 25 Squad Builder</title>
  <style>
    body {
      background-color: #0b2a2f;
      color: white;
      font-family: sans-serif;
      text-align: center;
    }
    h1 {
      margin-top: 20px;
    }
    .field {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
      margin: 40px auto;
      max-width: 800px;
    }
    .position {
      background: #1c4c54;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 8px #0ff;
      min-height: 180px;
    }
    .player-img {
      width: 100px;
      height: 140px;
      object-fit: cover;
      border: 2px solid white;
      border-radius: 8px;
      cursor: grab;
    }
    .bench {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin: 20px;
    }
    .dropzone {
      min-height: 140px;
      display: flex;
      justify-content: center;
      align-items: center;
      border: 2px dashed white;
      border-radius: 8px;
    }
  </style>
</head>
<body>

<h1>EAFC 25 – Squad Builder (Drag & Drop)</h1>

<div class="bench" id="bench">
  <img src="https://cdn.sofifa.net/players/231/747/24_120.png" draggable="true" class="player-img" data-name="Mbappé" data-rating="91" data-nation="France" data-club="PSG">
  <img src="https://cdn.sofifa.net/players/239/085/24_120.png" draggable="true" class="player-img" data-name="Haaland" data-rating="91" data-nation="Norway" data-club="Man City">
  <img src="https://cdn.sofifa.net/players/202/126/24_120.png" draggable="true" class="player-img" data-name="Kane" data-rating="89" data-nation="England" data-club="Bayern">
  <img src="https://cdn.sofifa.net/players/177/003/24_120.png" draggable="true" class="player-img" data-name="Modrić" data-rating="87" data-nation="Croatia" data-club="Real Madrid">
  <img src="https://cdn.sofifa.net/players/247/635/24_120.png" draggable="true" class="player-img" data-name="Bellingham" data-rating="86" data-nation="England" data-club="Real Madrid">
  <img src="https://cdn.sofifa.net/players/193/080/24_120.png" draggable="true" class="player-img" data-name="De Gea" data-rating="85" data-nation="Spain" data-club="Free Agent">
</div>

<div class="field">
  <div class="position dropzone" data-position="Torwart"></div>
  <div class="position dropzone" data-position="Mittelfeld"></div>
  <div class="position dropzone" data-position="Stürmer"></div>
</div>

<h2 id="summary">Durchschnittliches Rating: 0 | Chemie: 0</h2>

<script>
  const dropzones = document.querySelectorAll('.dropzone');
  const summary = document.getElementById('summary');
  const bench = document.getElementById('bench');

  function makeDraggable(img) {
    img.addEventListener('dragstart', (e) => {
      e.dataTransfer.setData('text/plain', JSON.stringify({
        outerHTML: e.target.outerHTML,
        name: e.target.dataset.name
      }));
    });
  }

  document.querySelectorAll('.player-img').forEach(makeDraggable);

  dropzones.forEach(zone => {
    zone.addEventListener('dragover', (e) => e.preventDefault());
    zone.addEventListener('drop', (e) => {
      e.preventDefault();
      const data = JSON.parse(e.dataTransfer.getData('text/plain'));
      const newPlayer = document.createElement('div');
      newPlayer.innerHTML = data.outerHTML;
      const img = newPlayer.firstChild;
      img.addEventListener('click', () => {
        bench.appendChild(img);
        updateStats();
      });
      zone.innerHTML = '';
      zone.appendChild(img);
      updateStats();
    });
  });

  function updateStats() {
    let totalRating = 0;
    let count = 0;
    let nations = [];
    let clubs = [];

    dropzones.forEach(zone => {
      const img = zone.querySelector('img');
      if (img) {
        const rating = parseInt(img.dataset.rating);
        totalRating += rating;
        nations.push(img.dataset.nation);
        clubs.push(img.dataset.club);
        count++;
      }
    });

    const average = count > 0 ? (totalRating / count).toFixed(1) : 0;
    const nationBonus = getMostCommonCount(nations);
    const clubBonus = getMostCommonCount(clubs);
    const chemie = Math.min(nationBonus + clubBonus, count);

    summary.textContent = `Durchschnittliches Rating: ${average} | Chemie: ${chemie}/${count}`;
  }

  function getMostCommonCount(arr) {
    const map = {};
    arr.forEach(val => map[val] = (map[val] || 0) + 1);
    return arr.length ? Math.max(...Object.values(map)) : 0;
  }
</script>

</body>
</html>

 





