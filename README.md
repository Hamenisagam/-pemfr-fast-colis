# -pemfr-fast-colis
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>PEMFR Fast Colis</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f4f7fb;
  color: #172033;
}

header {
  background: #0b2d5c;
  color: white;
  padding: 22px;
  text-align: center;
  font-size: 24px;
  font-weight: bold;
}

.container {
  max-width: 600px;
  margin: 50px auto;
  padding: 20px;
}

.card {
  background: white;
  padding: 30px;
  border-radius: 18px;
  box-shadow: 0 8px 25px rgba(0,0,0,0.08);
}

h1 {
  text-align: center;
}

.description {
  text-align: center;
  color: #64748b;
}

input {
  width: 100%;
  padding: 15px;
  margin-top: 20px;
  border: 1px solid #cbd5e1;
  border-radius: 10px;
  font-size: 16px;
}

button {
  width: 100%;
  padding: 15px;
  margin-top: 12px;
  background: #1261c9;
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 16px;
  font-weight: bold;
}

button:active {
  opacity: 0.8;
}

#result {
  display: none;
  margin-top: 25px;
}

.status {
  font-size: 20px;
  font-weight: bold;
  margin: 10px 0 20px;
}

.step {
  padding: 14px;
  border-left: 4px solid #1261c9;
  margin-bottom: 10px;
  background: #f8fafc;
  border-radius: 5px;
}

.error {
  display: none;
  color: #b91c1c;
  margin-top: 15px;
  text-align: center;
}

.footer {
  text-align: center;
  color: #64748b;
  font-size: 13px;
  margin-top: 25px;
}
</style>
</head>

<body>

<header>
PEMFR Fast Colis
</header>

<div class="container">

<div class="card">

<h1>Suivez votre colis</h1>

<p class="description">
Entrez votre numéro de suivi pour connaître l'état de votre colis.
</p>

<input
type="text"
id="trackingNumber"
placeholder="Exemple : PEMFR123456"
>

<button onclick="searchPackage()">
Rechercher
</button>

<div id="error" class="error">
Numéro de suivi introuvable.
</div>

<div id="result">

<p><strong>Numéro de suivi :</strong></p>

<p id="number"></p>

<div class="status" id="status"></div>

<div class="step">
✓ Colis enregistré
</div>

<div class="step">
✓ Colis expédié
</div>

<div class="step">
● Colis en transit
</div>

<div class="step">
○ En livraison
</div>

<div class="step">
○ Livré
</div>

</div>

<div class="footer">
PEMFR Fast Colis — Service de suivi
</div>

</div>

</div>

<script>

function searchPackage() {

let number =
document.getElementById("trackingNumber").value.trim();

let result =
document.getElementById("result");

let error =
document.getElementById("error");

let numberDisplay =
document.getElementById("number");

let status =
document.getElementById("status");

/*
Numéro de démonstration.
*/

if (number.toUpperCase() === "PEMFR123456") {

error.style.display = "none";

result.style.display = "block";

numberDisplay.innerText = number.toUpperCase();

status.innerText = "Statut : En transit";

} else {

result.style.display = "none";

error.style.display = "block";

}

}

</script>

</body>
</html>
