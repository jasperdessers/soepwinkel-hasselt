<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soepwinkel Hasselt</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            line-height: 1.6;
            background-color: #f9f9f9;
        }
        header {
            background-color: #f05a28;
            color: white;
            padding: 20px 0;
            text-align: center;
        }
        .container {
            padding: 20px;
        }
        .soep {
            border: 1px solid #ddd;
            border-radius: 5px;
            margin: 15px 0;
            padding: 15px;
            background-color: #fff;
        }
        .soep h3 {
            margin: 0 0 10px;
        }
        .bestel-btn {
            background-color: #f05a28;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
        }
        .bestel-btn:hover {
            background-color: #d94e24;
        }
        form {
            margin-top: 20px;
            border: 1px solid #ddd;
            padding: 15px;
            background-color: #fff;
            border-radius: 5px;
        }
        form input, form select, form textarea, form button {
            display: block;
            width: 100%;
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: #333;
            color: white;
            position: absolute;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welkom bij Soepwinkel Hasselt</h1>
        <p>De lekkerste soepen, vers gemaakt voor jou in Hasselt, en gratis geleverd op maandag tussen 17u en 20u!</p>
    </header>

    <div class="container">
        <h2>Onze Soepen</h2>
        <div class="soep">
            <h3>Tomatensoep</h3>
            <p>Heerlijke verse tomatensoep met basilicum. €8,00 per liter.</p>
            <button class="bestel-btn" onclick="openForm('Tomatensoep')">Bestel Nu</button>
        </div>
        <div class="soep">
            <h3>groene soep</h3>
            <p>Traditionele groene soep. €7,50 per liter.</p>
            <button class="bestel-btn" onclick="openForm('Erwtensoep')">Bestel Nu</button>
        </div>

        <form id="orderForm" style="display: none;">
            <h2>Bestel Formulier</h2>
            <label for="soep">Soep:</label>
            <input type="text" id="soep" name="soep" readonly>

            <label for="naam">Naam:</label>
            <input type="text" id="naam" name="naam" placeholder="Vul je naam in" required>

            <label for="email">E-mailadres:</label>
            <input type="email" id="email" name="email" placeholder="Vul je e-mailadres in" required>

            <label for="hoeveelheid">Hoeveelheid (liters):</label>
            <input type="number" id="hoeveelheid" name="hoeveelheid" placeholder="Bijv. 2" required>

            <label for="adres">woonplaats:</label>
            <input type="adres" id="adres" name="adres" placeholder="Vul je adres in" required>

            <label for="opmerkingen">Opmerkingen:</label>
            <textarea id="opmerkingen" name="opmerkingen" placeholder="Eventuele allergieën of andere opmerkingen"></textarea>

            <button type="submit">Bestelling Plaatsen</button>
        </form>
    </div>

    <footer>
        <p>© 2024 Soepwinkel Hasselt</p>
    </footer>

    <script>
        function openForm(soepNaam) {
            document.getElementById('orderForm').style.display = 'block';
            document.getElementById('soep').value = soepNaam;
            window.scrollTo(0, document.getElementById('orderForm').offsetTop);
        }

        document.getElementById('orderForm').addEventListener('submit', function(event) {
            event.preventDefault();
            alert('Bedankt voor je bestelling! Wij nemen contact met je op ter bevestiging.');
            document.getElementById('orderForm').reset();
            document.getElementById('orderForm').style.display = 'none';
        });
    </script>
</body>
</html>
