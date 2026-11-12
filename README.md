# tip--calculator
https://onecompiler.com/html/458snesx4



<!DOCTYPE html>
<html>
<head>
    <title>Tip Calculator</title>

    <style>
        body {
            font-family: Arial;
            background-color: black;
            text-align: center;
            padding: 30px;
        }

        .container {
            background: white;
            padding: 25px;
            border-radius: 10px;
            max-width: 350px;
            margin: auto;
        }

        input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
        }

        button {
            padding: 10px 20px;
            background: black;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>

<body>

<div class="container">

    <h2>Tip Calculator</h2>

    <input type="number" id="bill"
        placeholder="Enter Bill Amount">

    <input type="number" id="tip"
        placeholder="Enter Tip Percentage">

    <br>

    <button onclick="calculateTip()">Calculate</button>

    <p id="result">Tip and Total will appear here</p>

</div>

<script>
function calculateTip() {

    let bill = document.getElementById("bill").value;
    let tipPercent = document.getElementById("tip").value;
    let result = document.getElementById("result");

    bill = Number(bill);
    tipPercent = Number(tipPercent);

    if (
        document.getElementById("bill").value.trim() === "" ||
        document.getElementById("tip").value.trim() === "" ||
        !Number.isFinite(bill) ||
        !Number.isFinite(tipPercent) ||
        bill <= 0 ||
        tipPercent < 0
    ) {
        result.innerHTML =
            "Invalid input! Enter a valid bill and tip percentage.";
        return;
    }

    let tipAmount = bill * (tipPercent / 100);
    let total = bill + tipAmount;

    result.innerHTML =
        "Tip: ₱" + tipAmount.toFixed(2) +
        "<br>Total: ₱" + total.toFixed(2);
}
</script>

</body>
</html>

