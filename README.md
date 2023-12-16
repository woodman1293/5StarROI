
    <h1>Five Star Reviews ROI Investment Calculator
    Monthly investment $495</h1>

    <form id="calculatorForm">
        <label for="missedCustomers">Missed Customers Going to Competition:</label>
        <input type="number" id="missedCustomers" required><br>

        <label for="customerValue">Average Value of Each Customer:</label>
        <input type="number" id="customerValue" required><br>

        <label for="customersGained">Number of Customers Gained through Self-Generated Reviews:</label>
        <input type="number" id="customersGained" required><br>

        <button type="submit">Calculate</button>
    </form>

    <div id="result"></div>

    <script>
        document.getElementById("calculatorForm").addEventListener("submit", function(event) {
            event.preventDefault();
            var missedCustomers = parseInt(document.getElementById("missedCustomers").value);
            var customerValue = parseInt(document.getElementById("customerValue").value);
            var customersGained = parseInt(document.getElementById("customersGained").value);
            var costPerMonth = 295;

            var roi = (missedCustomers * customerValue) - (costPerMonth) + customersGained;
            var roiFormatted = roi.toLocaleString(undefined, {maximumFractionDigits: 2});

            document.getElementById("result").innerHTML = "The Return on Investment (ROI) for using Five Star Reviews to Dominate your Competition is $" + roiFormatted + " per month.";

            var value = roi - costPerMonth;
            if (value > 0) {
                document.getElementById("result").innerHTML += "<br>The implementation of these services provides a value of $" + value.toFixed(2) + " per month.";
            } else if (value === 0) {
                document.getElementById("result").innerHTML += "<br>The implementation of these services breaks even with the cost.";
            } else {
                document.getElementById("result").innerHTML += "<br>The implementation of these services results in a loss of $" + Math.abs(value).toFixed(2) + " per month.";
            }
        });
    </script>
</body>
</html>

