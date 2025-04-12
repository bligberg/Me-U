# Me-U
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Notre compte à rebours d'amour</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #fff9f9;
      color: #333;
      text-align: center;
      padding-top: 50px;
    }
    h2 {
      color: #c2185b;
    }
    .barre {
      width: 80%;
      margin: 20px auto;
      background-color: #eee;
      border-radius: 15px;
      height: 30px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .progression {
      height: 100%;
      width: 17,13%;
      background: linear-gradient(90deg, #f06292, #ba68c8);
      border-radius: 15px;
      color: white;
      text-align: center;
      line-height: 30px;
      transition: width 0.5s ease;
    }
    p {
      font-size: 18px;
    }
  </style>
</head>
<body>

<h2>Compte à rebours jusqu'à notre mariage</h2>
<p id="info"></p>

<div class="barre">
  <div class="progression" id="progressionBar">0%</div>
</div>

<script>
  const debut = new Date("2024-04-07");
  const fin = new Date("2030-03-06");
  const maintenant = new Date();

  const totalJours = Math.ceil((fin - debut) / (1000 * 60 * 60 * 24));
  const joursPasses = Math.ceil((maintenant - debut) / (1000 * 60 * 60 * 24));
  const joursRestants = totalJours - joursPasses;

  let pourcentage = Math.min((joursPasses / totalJours) * 100, 100).toFixed(2);

  const barre = document.getElementById("progressionBar");
  barre.style.width = pourcentage + "%";
  barre.innerText = pourcentage + "%";

  const info = document.getElementById("info");
  if (joursRestants > 0) {
    info.innerText = `Jour ${joursPasses} sur ${totalJours} — Il reste ${joursRestants} jours avant notre mariage !`;
  } else {
    info.innerText = "C'est notre jour J ! Félicitations !";
  }
</script>

</body>
</html>
