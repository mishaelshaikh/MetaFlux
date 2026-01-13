<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Smartify

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #141e30, #243b55);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: white;
        }

        .box {
            background: #ffffff;
            color: black;
            padding: 30px;
            border-radius: 12px;
            width: 360px;
            text-align: center;
            box-shadow: 0px 10px 25px rgba(0,0,0,0.3);
        }

        h1 {
            margin-bottom: 10px;
            color: #243b55;
        }

        input, select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 6px;
            border: 1px solid #ccc;
        }

        button {
            width: 100%;
            padding: 10px;
            background: #243b55;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
        }

        button:hover {
            background: #141e30;
        }

        .result {
            margin-top: 15px;
            font-weight: bold;
        }
    </style>
</head>

<body>

<div class="box">
    <h1>Smartify</h1>
    <p>Your Free Time</p>

    <input type="number" id="time" placeholder="Free time (minutes)">

    <select id="interest">
        <option value="coding">Coding</option>
        <option value="revision">Revision</option>
        <option value="skills">Skill Building</option>
        <option value="wellness">Wellness</option>
    </select>

    <button onclick="getSuggestion()">Get Recommendation</button>

    <div class="result" id="output"></div>
</div>

<script>
function getSuggestion() {
    let time = document.getElementById("time").value;
    let interest = document.getElementById("interest").value;
    let output = document.getElementById("output");

    if (time <= 0) {
        output.innerHTML = "⚠ Please enter valid time.";
        return;
    }

    let suggestion = "";

    if (interest === "coding") {
        suggestion = time < 30
            ? "Solve 1 coding problem"
            : "Work on a mini coding project";
    }
    else if (interest === "revision") {
        suggestion = time < 30
            ? "Revise formulas or notes"
            : "Practice previous year questions";
    }
    else if (interest === "skills") {
        suggestion = time < 30
            ? "Watch a short skill tutorial"
            : "Practice hands-on skill task";
    }
    else if (interest === "wellness") {
        suggestion = time < 30
            ? "Do breathing exercises"
            : "Meditation or light workout";
    }

    output.innerHTML = "✅ Recommended Task:<br>" + suggestion;
}
</script>

</body>
</html># MetaFlux
