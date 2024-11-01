<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Slotmaschine - Deutsch Würfeln</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            background-color: #f4f4f4;
        }
        h1 {
            color: #333;
        }
        .slot-machine {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        .slot {
            border: 2px solid #333;
            border-radius: 10px;
            width: 100px;
            height: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 24px;
            margin: 0 10px;
            background-color: #fff;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 18px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #218838;
        }
        .result {
            margin-top: 20px;
            font-size: 24px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>Slotmaschine - Deutsch Würfeln</h1>
    <div class="slot-machine">
        <div class="slot" id="slot1">Verb</div>
        <div class="slot" id="slot2">Zeitform</div>
        <div class="slot" id="slot3">Person</div>
    </div>
    <button onclick="wurf()">Würfeln!</button>
    <div class="result" id="result"></div>

    <script>
        const personen = ["Ich", "Du", "Er", "Sie", "Es", "Wir", "Ihr", "Sie"];
        const zeiten = ["Präsens", "Präteritum", "Perfekt"];
        const verben = [
            "essen", "trinken", "lesen", "spielen", "fahren", "laufen", "sehen", "schreiben",
            "arbeiten", "reisen", "singen", "tanzen", "zeichnen", "kaufen", "verkaufen",
            "beginnen", "beenden", "öffnen", "schließen", "fragen", "antworten", "kommen", "gehen",
            "bleiben", "finden", "nehmen", "geben", "vergessen", "erinnern", "denken", "wissen",
            "mögen", "lieben", "hassen", "bringen", "rufen", "schicken", "bitten", "helfen",
            "spazieren", "telefonieren", "hören", "sehen", "lesen", "sprechen", "schreiben", "spielen",
            "zeichnen", "fühlen", "schlafen", "wachen", "verstehen", "glauben", "sagen", "sitzen",
            "stehen", "liegen", "suchen", "nehmen", "halten", "machen", "arbeiten", "kaufen",
            "verleihen", "leihen", "lachen", "weinen", "freuen", "ärgern", "ängstigen", "beruhigen",
            "versichern", "einladen", "besuchen", "verreisen", "verweilen", "ausruhen", "entspannen",
            "bringen", "versprechen", "unterhalten", "prüfen", "analysieren", "diskutieren", "entwerfen",
            "entdecken", "entwickeln", "gestalten", "produzieren", "verarbeiten", "reparieren", "steuern",
            "modifizieren", "evaluieren", "abstimmen", "schätzen", "kalkulieren", "prognostizieren",
            "kommentieren", "unterstützen", "leiten", "organisieren", "planen", "verwalten", "lehren",
            "lernen", "forschen", "experimentieren", "vermitteln", "äußern", "unterrichten", "trainieren",
            "begleiten", "überprüfen", "aufzeichnen", "festlegen", "auswählen", "gewinnen", "verlieren",
            "überlegen", "rechnen", "vergleichen", "erklären", "berichtigen", "einsetzen", "vorbereiten"
        ];

        function wurf() {
            // Slotmaschine Animation starten
            animateSlots();

            // Verzögerung für die Slotmaschine
            setTimeout(() => {
                const person = personen[Math.floor(Math.random() * personen.length)];
                const zeit = zeiten[Math.floor(Math.random() * zeiten.length)];
                const verb = verben[Math.floor(Math.random() * verben.length)];

                // Ergebnisse in den Slots anzeigen
                document.getElementById("slot1").innerText = verb;
                document.getElementById("slot2").innerText = zeit;
                document.getElementById("slot3").innerText = person;

                // Ergebnisse unter den Slots anzeigen
                document.getElementById("result").innerHTML = `Ergebnis: ${verb}, ${zeit}, ${person}`;
            }, 1000); // Zeit für die Animation
        }

        function animateSlots() {
            const slots = document.querySelectorAll('.slot');
            slots.forEach(slot => {
                slot.innerText = '...'; // Platzhalter während der Animation
            });
        }
    </script>

</body>
</html>
