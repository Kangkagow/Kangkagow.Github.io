<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SmartDash - Text Expander</title>
<style>
body { font-family: Arial, sans-serif; background: #1e1e1e; color: #f5f5f5; padding: 20px; }
h2 { text-align: center; margin-bottom: 15px; }
.container { max-width: 480px; margin: auto; background: #2a2a2a; padding: 20px; border-radius: 12px; }
label { display: block; margin-top: 10px; font-weight: bold; }
input, button { width: 100%; padding: 10px; margin: 5px 0 10px; border-radius: 6px; border: none; }
button { background-color: #4caf50; color: white; font-weight: bold; }
#result { margin-top: 10px; font-weight: bold; background: #121212; padding: 10px; border-radius: 6px; word-wrap: break-word; }
.info { font-size: 0.9em; color: #ccc; margin-bottom: 10px; }
</style>
</head>
<body>

<div class="container">
<h2>SmartDash - Text Expander</h2>

<p class="info">Type an abbreviation below and press "Expand" to see the full text. Example: ty → Thank you, brb → Be right back.</p>

<label for="abbrev">Enter Abbreviation:</label>
<input type="text" id="abbrev" placeholder="Example: ty">

<button onclick="expandText()">Expand</button>
<button onclick="copyResult()">Copy to Clipboard</button>

<label for="result">Expanded Text:</label>
<div id="result">Your expanded text will appear here</div>

</div>

<script>
function expandText() {
    const input = document.getElementById('abbrev').value.toLowerCase().trim();

    // Real abbreviations map (500+ can be added in this same pattern)
    const abbrevMap = {
        ty:"Thank you",
        brb:"Be right back",
        omw:"On my way",
        idk:"I don't know",
        lol:"Laugh out loud",
        btw:"By the way",
        fyi:"For your information",
        np:"No problem",
        asap:"As soon as possible",
        gtg:"Got to go",
        tbh:"To be honest",
        jk:"Just kidding",
        omg:"Oh my God",
        smh:"Shaking my head",
        rn:"Right now",
        thx:"Thanks",
        cya:"See you",
        bc:"Because",
        bbl:"Be back later",
        ikr:"I know, right",
        afk:"Away from keyboard",
        atm:"At the moment",
        bff:"Best friends forever",
        dm:"Direct message",
        ftw:"For the win",
        fomo:"Fear of missing out",
        gl:"Good luck",
        hf:"Have fun",
        gg:"Good game",
        gr8:"Great",
        ily:"I love you",
        l8r:"Later",
        msg:"Message",
        yw:"You're welcome",
        wb:"Welcome back",
        wfh:"Work from home",
        wtv:"Whatever"
        // You can continue adding more real abbreviations up to 500+
    };

    const expanded = abbrevMap[input] || "No expansion found";
    document.getElementById('result').innerText = expanded;
}

// Copy result to clipboard
function copyResult() {
    const resultText = document.getElementById('result').innerText;
    navigator.clipboard.writeText(resultText).then(() => {
        alert("Copied to clipboard!");
    }).catch(() => {
        alert("Copy failed.");
    });
}
</script>

</body>
</html>
