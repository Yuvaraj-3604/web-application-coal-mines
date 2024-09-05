<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carbon Footprint Quantification for Indian Coal Mines</title>
    <link rel="stylesheet" href="C:\Users\Yuvaraj Perumal V\OneDrive\Desktop\coal\style.css">
</head>
<body>
    <header>
        <h1>Carbon Footprint Quantification for Indian Coal Mines</h1>
        <p>Explore pathways to carbon neutrality</p>
    </header>

    <main>
        <section class="input-section">
            <h2>Input Data</h2>
            <form id="carbonForm">
                <label for="industryName">Industry Name:</label>
                <input type="text" id="industryName" name="industryName" required>

                <label for="coalProduction">Coal Production (tons):</label>
                <input type="number" id="coalProduction" name="coalProduction" required>

                <label for="emissionFactor">Emission Factor (kg CO2/ton):</label>
                <input type="number" id="emissionFactor" name="emissionFactor" required>

                <button type="submit">Calculate Carbon Footprint</button>
            </form>
        </section>

        <section class="results-section">
            <h2>Carbon Footprint Results</h2>
            <table id="resultsTable">
                <thead>
                    <tr>
                        <th>Industry Name</th>
                        <th>Coal Production (tons)</th>
                        <th>Emission Factor (kg CO2/ton)</th>
                        <th>Total Carbon Footprint (tons CO2)</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Coal India Limited</td>
                        <td>600,000</td>
                        <td>2.86</td>
                        <td>1,716,000</td>
                    </tr>
                    <tr>
                        <td>Singareni Collieries Company</td>
                        <td>400,000</td>
                        <td>2.90</td>
                        <td>1,160,000</td>
                    </tr>
                </tbody>
            </table>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Carbon Footprint Quantification. All rights reserved.</p>
    </footer>

    <script>
        document.getElementById('carbonForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const industryName = document.getElementById('industryName').value;
            const coalProduction = parseFloat(document.getElementById('coalProduction').value);
            const emissionFactor = parseFloat(document.getElementById('emissionFactor').value);
            const carbonFootprint = coalProduction * emissionFactor / 1000;

            const table = document.getElementById('resultsTable').getElementsByTagName('tbody')[0];
            const newRow = table.insertRow();

            const cell1 = newRow.insertCell(0);
            const cell2 = newRow.insertCell(1);
            const cell3 = newRow.insertCell(2);
            const cell4 = newRow.insertCell(3);

            cell1.textContent = industryName;
            cell2.textContent = coalProduction;
            cell3.textContent = emissionFactor;
            cell4.textContent = carbonFootprint.toFixed(2);
        });
    </script>
</body>
</html>
