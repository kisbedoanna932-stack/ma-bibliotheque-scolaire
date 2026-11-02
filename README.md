
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Ma Bibliothèque Scolaire – Burkina Faso</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f5f7f4;color:#203329}
header{background:#174b35;color:white;text-align:center;padding:25px 12px}
header h1{margin:0;font-size:25px}
main{max-width:900px;margin:auto;padding:20px 15px}
h2{color:#174b35}
.card,.panel{background:white;padding:20px;border-radius:13px;margin:15px 0;box-shadow:0 3px 12px #0001}
button{background:#174b35;color:white;border:0;border-radius:8px;padding:13px;margin:5px 0;width:100%;font-size:16px;cursor:pointer}
.back{background:#e4ece5;color:#174b35;width:auto}
.subject{background:white;color:#174b35;border:1px solid #d3dfd5;text-align:left}
.hidden{display:none}
p{line-height:1.6}
footer{text-align:center;padding:20px;color:#68766d}
</style>
</head>
<body>
<header>
<h1>🇧🇫 Ma Bibliothèque Scolaire</h1>
<p>Tout pour apprendre et enseigner</p>
</header>

<main>

<section id="home">
<h2 style="text-align:center">Bienvenue dans ta bibliothèque !</h2>
<p style="text-align:center">Une seule plateforme pour apprendre et enseigner au Burkina Faso.</p>

<div class="card">
<h2>📚 Espace élèves</h2>
<p>Cours, exercices, devoirs et corrigés.</p>
<button onclick="show('eleves')">Entrer dans l'espace élèves</button>
</div>

<div class="card">
<h2>👩‍🏫 Espace enseignants</h2>
<p>Préparation des cours et évaluations.</p>
<button onclick="show('enseignants')">Entrer dans l'espace enseignants</button>
</div>
</section>

<section id="eleves" class="hidden">
<button class="back" onclick="show('home')">← Accueil</button>
<h2>Espace élèves</h2>
<p>Choisis ta classe :</p>
<div class="card">
<button onclick="show('seconde')">2nde C</button>
<p>Les autres classes seront ajoutées progressivement.</p>
</div>
</section>

<section id="seconde" class="hidden">
<button class="back" onclick="show('eleves')">← Retour</button>
<h2>Classe de 2nde C</h2>
<p>Choisis ta matière :</p>
<div id="matieres"></div>
</section>

<section id="matiere" class="hidden">
<button class="back" onclick="show('seconde')">← Matières</button>
<h2 id="titreMatiere"></h2>
<div class="card">
<button onclick="show('cours')">📖 Cours</button>
<button onclick="show('exercices')">✍️ Exercices</button>
<button onclick="show('devoirs')">📝 Devoirs et compositions</button>
<button onclick="show('corriges')">✅ Corrigés</button>
</div>
</section>

<section id="cours" class="hidden">
<button class="back" onclick="show('matiere')">← Retour</button>
<h2>Cours</h2>
<p>Les leçons complètes seront ajoutées ici, avec définitions, explications et exemples.</p>
</section>

<section id="exercices" class="hidden">
<button class="back" onclick="show('matiere')">← Retour</button>
<h2>Exercices</h2>
<p>Des exercices d'application et d'entraînement seront disponibles ici.</p>
</section>

<section id="devoirs" class="hidden">
<button class="back" onclick="show('matiere')">← Retour</button>
<h2>Devoirs et compositions</h2>
<p>Des sujets d'entraînement seront ajoutés ici.</p>
</section>

<section id="corriges" class="hidden">
<button class="back" onclick="show('matiere')">← Retour</button>
<h2>Corrigés</h2>
<p>Les solutions détaillées seront ajoutées ici.</p>
</section>

<section id="enseignants" class="hidden">
<button class="back" onclick="show('home')">← Accueil</button>
<h2>Espace enseignants</h2>
<div class="card">
<h3>📚 Préparation des leçons</h3>
<p>Préparer les cours et leurs objectifs pédagogiques.</p>
</div>
<div class="card">
<h3>📋 Fiches pédagogiques</h3>
<p>Organiser les séquences et les activités d'apprentissage.</p>
</div>
<div class="card">
<h3>📝 Évaluations</h3>
<p>Préparer les devoirs, compositions et corrigés.</p>
</div>
<p>La connexion sécurisée des enseignants sera ajoutée ultérieurement.</p>
</section>

</main>

<footer>Ma Bibliothèque Scolaire – Burkina Faso</footer>

<script>
const noms=[
"Français",
"Histoire-Géographie",
"Anglais",
"Mathématiques",
"SVT",
"Physique-Chimie",
"Philosophie"
];

let pageActuelle="home";

function show(id){
document.querySelectorAll("main section").forEach(s=>s.classList.add("hidden"));
document.getElementById(id).classList.remove("hidden");
pageActuelle=id;
window.scrollTo(0,0);
}

const liste=document.getElementById("matieres");

noms.forEach(nom=>{
let bouton=document.createElement("button");
bouton.className="subject";
bouton.textContent="📘 "+nom;
bouton.onclick=()=>{
document.getElementById("titreMatiere").textContent=nom+" – 2nde C";
show("matiere");
};
liste.appendChild(bouton);
});
</script>
</body>
</html>

