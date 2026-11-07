
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DOM GAMING WORLD</title>
<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #101020;
  color: white;
  text-align: center;
}
header {
  background: linear-gradient(90deg,#6500ff,#008cff);
  padding: 25px;
}
h1 { margin: 0; }
input {
  padding: 14px;
  width: 80%;
  max-width: 400px;
  margin: 20px;
  border-radius: 10px;
  border: none;
}
.games {
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(140px,1fr));
  gap: 15px;
  padding: 15px;
}
.game {
  background: #242442;
  padding: 25px 10px;
  border-radius: 12px;
}
.game a {
  color: #50c8ff;
  text-decoration: none;
  font-weight: bold;
}
.game:hover { background: #41416b; }
</style>
</head>
<body>
<header>
<h1>🎮 DOM GAMING WORLD</h1>
<p>Play games and have fun!</p>
</header>
<input id="search" placeholder="🔍 Search games..." oninput="filterGames()">
<div class="games" id="games"></div>
<script>
const games = [
["Roblox","https://www.roblox.com"],
["Minecraft","https://classic.minecraft.net"],
["2048","https://play2048.co"],
["Tetris","https://tetris.com/play-tetris"],
["Slope","https://slope-game.github.io"],
["Pac-Man","https://www.google.com/search?q=play+pacman"],
["Chess","https://www.chess.com/play/computer"],
["Basketball","https://www.google.com/search?q=play+online+basketball+game"],
["Soccer","https://www.ea.com/games/ea-sports-fc"],
["Car Racing","https://poki.com/en/racing"],
["Subway Surfers","https://poki.com/en/g/subway-surfers"],
["Temple Run","https://poki.com"],
["Stickman","https://poki.com"],
["Moto X3M","https://poki.com/en/moto-x3m"],
["Drift Hunters","https://www.drifthunters.com"],
["Fireboy and Watergirl","https://www.coolmathgames.com"],
["Crossy Road","https://poki.com"],
["Among Us","https://www.innersloth.com/games/among-us/"],
["Cookie Clicker","https://orteil.dashnet.org/cookieclicker/"],
["Geometry Dash","https://www.robtopgames.com"]
];

for(let i=21;i<=60;i++){
 games.push(["Arcade Game "+i,"https://poki.com"]);
}

function showGames(list){
 document.getElementById("games").innerHTML=list.map(g=>
 `<div class="game"><a href="${g[1]}" target="_blank" rel="noopener">${g[0]} 🎮</a></div>`
 ).join("");
}
function filterGames(){
 const q=document.getElementById("search").value.toLowerCase();
 showGames(games.filter(g=>g[0].toLowerCase().includes(q)));
}
showGames(games);
</script>
</body>
</html>
