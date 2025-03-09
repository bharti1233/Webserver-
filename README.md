<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dark Fire Prediction</title>

    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap" rel="stylesheet">

    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            background-color: #0a0a0a;
            color: white;
            font-family: 'Poppins', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            padding: 10px;
        }
        .container {
            width: 90%;
            max-width: 350px;
            padding: 20px;
            background: rgba(20, 20, 20, 0.9);
            border-radius: 10px;
            box-shadow: 0 0 15px red;
        }
        h1 {
            font-size: 24px;
            color: red;
            font-weight: bold;
            text-shadow: 0 0 10px red, 0 0 20px red;
        }
        .box {
            display: inline-block;
            padding: 8px 12px;
            font-size: 18px;
            font-weight: bold;
            margin: 5px;
            border-radius: 5px;
            border: 2px solid red;
            text-shadow: 0 0 10px red;
        }
        .period-box { color: yellow; }
        .big { color: lightblue; }
        .small { color: orange; }
        .number-box { color: green; }
        .predict-btn {
            padding: 10px 15px;
            font-size: 14px;
            background: white;
            color: black;
            font-weight: bold;
            border: none;
            cursor: pointer;
            margin-top: 15px;
            border-radius: 5px;
            transition: all 0.3s ease-in-out;
        }
        .predict-btn:hover {
            background: lightgray;
            transform: scale(1.05);
        }
        #live-result {
            font-size: 14px;
            font-weight: bold;
            color: white;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <div id="prediction-page" class="container">
        <h1>🔥 乂ᴅᴀʀᴋ乡ғɪʀᴇ Crack by ZRX PAPA 🔥</h1>
        <p id="result" class="result">PERIOD: <span class="box period-box">--</span></p>
        <p id="signal" class="signal">SIGNAL: <span class="box">--</span></p>
        <p id="prediction" class="prediction">PREDICTED NUMBERS: <span class="box number-box">--/--</span></p>
        <p id="live-result">LIVE UPDATING...</p>
        <button class="predict-btn" onclick="fetchPrediction()">Predict</button>
    </div>

    <script>
        const API_URL = 'https://api.bdg88zf.com/api/webapi/GetGameIssue';
        const REQUEST_DATA = {
            typeId: 1,
            language: 0,
            random: "e7fe6c090da2495ab8290dac551ef1ed",
            signature: "1F390E2B2D8A55D693E57FD905AE73A7",
            timestamp: 1723726679
        };

        let periodResults = {}; // Store results for each period

        function fetchPrediction() {
            fetch(API_URL, {
                method: "POST",
                headers: {
                    "Content-Type": "application/json;charset=UTF-8"
                },
                body: JSON.stringify(REQUEST_DATA)
            })
            .then(response => response.json())
            .then(data => {
                if (data && data.data) {
                    let issueNumber = data.data.issueNumber || "Unknown";

                    if (!periodResults[issueNumber]) {
                        // Apply systematic prediction method
                        let lastDigit = parseInt(issueNumber.slice(-1)); // Extract last digit of period
                        let num1 = (lastDigit * 3 + 7) % 10; // Algorithm to predict number 1
                        let num2 = (num1 + 5) % 10; // Algorithm to predict number 2

                        // Big-Small Decision Based on Sum of Period Digits
                        let sumDigits = issueNumber.split('').reduce((acc, num) => acc + parseInt(num), 0);
                        let bigSmallPrediction = sumDigits % 2 === 0 ? "Big" : "Small";

                        // Store result for this period
                        periodResults[issueNumber] = {
                            bigSmallPrediction,
                            predictedNumbers: `${num1}/${num2}`
                        };
                    }

                    let { bigSmallPrediction, predictedNumbers } = periodResults[issueNumber];

                    document.getElementById("result").innerHTML = `PERIOD: <span class="box period-box">${issueNumber}</span>`;
                    document.getElementById("signal").innerHTML = `SIGNAL: <span class="box ${bigSmallPrediction.toLowerCase()}">${bigSmallPrediction}</span>`;
                    document.getElementById("prediction").innerHTML = `PREDICTED NUMBERS: <span class="box number-box">${predictedNumbers}</span>`;
                    document.getElementById("live-result").innerHTML = "✅ LIVE DATA UPDATED!";
                } else {
                    document.getElementById("live-result").innerHTML = "⚠️ ERROR!";
                }
            })
            .catch(error => {
                document.getElementById("live-result").innerHTML = "⚠️ ERROR!";
                console.error("API Fetch Error:", error);
            });
        }

        setInterval(fetchPrediction, 10000);
    </script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dark Fire Prediction</title>

    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap" rel="stylesheet">

    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            background-color: #0a0a0a;
            color: white;
            font-family: 'Poppins', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            text-align: center;
            padding: 10px;
        }
        .container {
            width: 90%;
            max-width: 350px;
            padding: 20px;
            background: rgba(20, 20, 20, 0.9);
            border-radius: 10px;
            box-shadow: 0 0 15px red;
        }
        h1 {
            font-size: 24px;
            color: red;
            font-weight: bold;
            text-shadow: 0 0 10px red, 0 0 20px red;
        }
        .box {
            display: inline-block;
            padding: 8px 12px;
            font-size: 18px;
            font-weight: bold;
            margin: 5px;
            border-radius: 5px;
            border: 2px solid red;
            text-shadow: 0 0 10px red;
        }
        .period-box { color: yellow; }
        .big { color: lightblue; }
        .small { color: orange; }
        .number-box { color: green; }
        .predict-btn {
            padding: 10px 15px;
            font-size: 14px;
            background: white;
            color: black;
            font-weight: bold;
            border: none;
            cursor: pointer;
            margin-top: 15px;
            border-radius: 5px;
            transition: all 0.3s ease-in-out;
        }
        .predict-btn:hover {
            background: lightgray;
            transform: scale(1.05);
        }
        #live-result {
            font-size: 14px;
            font-weight: bold;
            color: white;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <div id="prediction-page" class="container">
        <h1>🔥 乂ᴅᴀʀᴋ乡ғɪʀᴇ Crack by ZRX PAPA 🔥</h1>
        <p id="result" class="result">PERIOD: <span class="box period-box">--</span></p>
        <p id="signal" class="signal">SIGNAL: <span class="box">--</span></p>
        <p id="prediction" class="prediction">PREDICTED NUMBERS: <span class="box number-box">--/--</span></p>
        <p id="live-result">LIVE UPDATING...</p>
        <button class="predict-btn" onclick="fetchPrediction()">Predict</button>
    </div>

    <script>
        const API_URL = 'https://api.bdg88zf.com/api/webapi/GetGameIssue';
        const REQUEST_DATA = {
            typeId: 1,
            language: 0,
            random: "e7fe6c090da2495ab8290dac551ef1ed",
            signature: "1F390E2B2D8A55D693E57FD905AE73A7",
            timestamp: 1723726679
        };

        let periodResults = {}; // Store results for each period

        function fetchPrediction() {
            fetch(API_URL, {
                method: "POST",
                headers: {
                    "Content-Type": "application/json;charset=UTF-8"
                },
                body: JSON.stringify(REQUEST_DATA)
            })
            .then(response => response.json())
            .then(data => {
                if (data && data.data) {
                    let issueNumber = data.data.issueNumber || "Unknown";

                    if (!periodResults[issueNumber]) {
                        // Apply systematic prediction method
                        let lastDigit = parseInt(issueNumber.slice(-1)); // Extract last digit of period
                        let num1 = (lastDigit * 3 + 7) % 10; // Algorithm to predict number 1
                        let num2 = (num1 + 5) % 10; // Algorithm to predict number 2

                        // Big-Small Decision Based on Sum of Period Digits
                        let sumDigits = issueNumber.split('').reduce((acc, num) => acc + parseInt(num), 0);
                        let bigSmallPrediction = sumDigits % 2 === 0 ? "Big" : "Small";

                        // Store result for this period
                        periodResults[issueNumber] = {
                            bigSmallPrediction,
                            predictedNumbers: `${num1}/${num2}`
                        };
                    }

                    let { bigSmallPrediction, predictedNumbers } = periodResults[issueNumber];

                    document.getElementById("result").innerHTML = `PERIOD: <span class="box period-box">${issueNumber}</span>`;
                    document.getElementById("signal").innerHTML = `SIGNAL: <span class="box ${bigSmallPrediction.toLowerCase()}">${bigSmallPrediction}</span>`;
                    document.getElementById("prediction").innerHTML = `PREDICTED NUMBERS: <span class="box number-box">${predictedNumbers}</span>`;
                    document.getElementById("live-result").innerHTML = "✅ LIVE DATA UPDATED!";
                } else {
                    document.getElementById("live-result").innerHTML = "⚠️ ERROR!";
                }
            })
            .catch(error => {
                document.getElementById("live-result").innerHTML = "⚠️ ERROR!";
                console.error("API Fetch Error:", error);
            });
        }

        setInterval(fetchPrediction, 10000);
    </script>

</body>
</html>
