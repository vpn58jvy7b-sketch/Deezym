
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#080d1b">
<title>DeezyM - Films et Mangas</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#080d1b;color:white;font-family:Arial}
header{padding:20px;background:#101a30}
.logo{font-size:30px;font-weight:bold;color:#40a5ff}
.logo span{color:white}
header p{color:#aab7ca}
main{padding:17px}
input{width:100%;padding:14px;border-radius:10px;border:0;background:#182640;color:white;font-size:16px}
nav{display:flex;gap:9px;overflow:auto;margin:18px 0}
nav button{border:0;border-radius:20px;padding:11px 15px;background:#192b47;color:white;white-space:nowrap}
nav button.active{background:#1688ed}
.hero{padding:25px;border-radius:15px;background:linear-gradient(130deg,#14518a,#252044);margin-bottom:25px}
.hero h1{font-size:27px}
.hero p{color:#d5e6f8;line-height:1.5}
h2{font-size:21px;margin-top:25px}
.grid{display:grid;grid-template-columns:repeat(2,1fr);gap:13px}
.card{background:#142139;border-radius:12px;overflow:hidden}
.poster{height:145px;background:linear-gradient(140deg,#225b85,#392653);display:flex;align-items:center;justify-content:center;font-size:45px}
.card h3{font-size:15px;margin:10px}
.card p{font-size:12px;color:#aab7ca;margin:0 10px 10px}
.watch{display:block;margin:10px;padding:10px;text-align:center;background:#1688ed;color:white;text-decoration:none;border-radius:8px;font-size:13px}
small{color:#aab7ca}
footer{text-align:center;padding:30px;color:#8798ad;font-size:12px}
</style>
</head>
<body>
<header>
<div class="logo">Deezy<span>M</span> 🎬</div>
<p>Films • Séries • Mangas • Animés</p>
</header>
<main>
<input id="search" placeholder="🔍 Rechercher un contenu...">

<nav>
<button class="active" onclick="show('Tous',this)">Tout</button>
<button onclick="show('Films',this)">Films</button>
<button onclick="show('Séries',this)">Séries</button>
<button onclick="show('Mangas',this)">Mangas</button>
<button onclick="show('Animés',this)">Animés</button>
</nav>

<section class="hero">
<h1>Bienvenue sur DeezyM</h1>
<p>Ton espace de découverte de films, séries et mangas.</p>
<small>Découvre les contenus disponibles légalement.</small>
</section>

<h2>🎬 Films du domaine public</h2>
<div class="grid" id="catalogue">

<div class="card" data-type="Films">
<div class="poster">🎞️</div>
<h3>Big Buck Bunny</h3>
<p>Film d'animation • Blender</p>
<a class="watch" href="https://peach.blender.org/" target="_blank">Découvrir le film ▶</a>
</div>

<div class="card" data-type="Films">
<div class="poster">🐑</div>
<h3>Films Blender</h3>
<p>Courts métrages libres</p>
<a class="watch" href="https://studio.blender.org/films/" target="_blank">Voir les films ▶</a>
</div>

<div class="card" data-type="Séries">
<div class="poster">📺</div>
<h3>Séries</h3>
<p>Catalogue à compléter</p>
<a class="watch" href="https://archive.org/details/movies" target="_blank">Explorer les archives ▶</a>
</div>

<div class="card" data-type="Mangas">
<div class="poster">📚</div>
<h3>Mangas</h3>
<p>Découvrir des œuvres</p>
<a class="watch" href="https://www.gutenberg.org/" target="_blank">Explorer les livres ▶</a>
</div>

<div class="card" data-type="Animés">
<div class="poster">🌸</div>
<h3>Animés</h3>
<p>Vidéos et animations</p>
<a class="watch" href="https://studio.blender.org/films/" target="_blank">Découvrir ▶</a>
</div>

</div>
</main>
<footer>© 2026 DeezyM • Les contenus doivent être autorisés à la diffusion.</footer>

<script>
function show(type,btn){
document.querySelectorAll('nav button').forEach(b=>b.classList.remove('active'));
btn.classList.add('active');
document.querySelectorAll('.card').forEach(c=>{
c.style.display=type==='Tous'||c.dataset.type===type?'block':'none';
});
}
document.getElementById('search').addEventListener('input',function(){
let q=this.value.toLowerCase();
document.querySelectorAll('.card').forEach(c=>{
c.style.display=c.innerText.toLowerCase().includes(q)?'block':'none';
});
});
</script>
</body>
</html>
