<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Foreman View - Labour System</title>
    <style>
        body { font-family: Arial; background:#0b1f3a; color:white; padding:15px; }
        h1, h3 { text-align:center; color: #60a5fa; }
        
        /* New Login Button Styling */
        .admin-nav {
            display: flex;
            justify-content: flex-end;
            margin-bottom: 10px;
        }
        .login-btn {
            background: #2563eb;
            color: white;
            text-decoration: none;
            padding: 8px 16px;
            border-radius: 5px;
            font-weight: bold;
            font-size: 14px;
            transition: background 0.3s;
            border: 1px solid #3b82f6;
        }
        .login-btn:hover {
            background: #1d4ed8;
        }

        .summary-box { background: #1e3a8a; padding: 20px; border-radius: 10px; display: flex; justify-content: space-around; margin-bottom: 20px; border: 1px solid #3b82f6; }
        .stat { text-align: center; }
        .stat h2 { margin: 0; font-size: 1.5rem; }
        table { width:100%; border-collapse: collapse; margin-top:10px; font-size:12px; }
        th, td { border:1px solid #334155; padding:8px; text-align:center; }
        th { background:#1e40af; }
        tr:nth-child(even) { background: #0f172a; }
    </style>
</head>
<body>

    <!-- Admin Access Navigation -->
    <div class="admin-nav">
        <a href="admin.html" class="login-btn">Admin Login</a>
    </div>

    <h1>Workforce Overview</h1>
    
    <div class="summary-box">
        <div class="stat"><h3>Total Arrears</h3><h2 id="sumArrears">Ksh 0</h2></div>
        <div class="stat"><h3>Total Paid (Spent)</h3><h2 id="sumPaid">Ksh 0</h2></div>
        <div class="stat"><h3>Total Due Balance</h3><h2 id="sumBalance">Ksh 0</h2></div>
    </div>

    <h3>Skilled Labour</h3>
    <table id="skilledTable">
        <thead><tr><th>Name</th><th>Rate</th><th>M</th><th>T</th><th>W</th><th>T</th><th>F</th><th>S</th><th>S</th><th>Days</th><th>Total</th><th>Arrears</th><th>Total Due</th><th>Paid</th><th>Balance</th></tr></thead>
        <tbody></tbody>
    </table>

    <h3>Casual Labour</h3>
    <table id="casualTable">
        <thead><tr><th>Name</th><th>Rate</th><th>M</th><th>T</th><th>W</th><th>T</th><th>F</th><th>S</th><th>S</th><th>Days</th><th>Total</th><th>Arrears</th><th>Total Due</th><th>Paid</th><th>Balance</th></tr></thead>
        <tbody></tbody>
    </table>

    <script>
        const API_URL = "YOUR_WEB_APP_URL_HERE";

        async function loadData() {
            try {
                const res = await fetch(API_URL);
                const data = await res.json();
                render(data);
            } catch (error) {
                console.error("Error loading data:", error);
            }
        }

        function formatMoney(n) { return "Ksh " + (n || 0).toLocaleString(); }

        function render(data) {
            let totals = { arrears: 0, paid: 0, balance: 0 };
            const tables = { Skilled: document.querySelector("#skilledTable tbody"), Casual: document.querySelector("#casualTable tbody") };
            
            Object.values(tables).forEach(t => t.innerHTML = "");

            data.forEach(w => {
                let daysArr = (w.Days || ",,,,,, ").split(",");
                let dayCount = 0;
                daysArr.forEach(d => { 
                    if(d.trim().toLowerCase() === 'y') dayCount += 1; 
                    if(d.trim().toLowerCase() === 'y/n') dayCount += 0.5; 
                });

                let weekTotal = dayCount * w.Rate;
                let totalDue = weekTotal + Number(w.Arrears);
                let balance = totalDue - Number(w.Paid);

                totals.arrears += Number(w.Arrears);
                totals.paid += Number(w.Paid);
                totals.balance += balance;

                // Create row with 7 day columns
                let row = `<tr>
                    <td>${w.Name}</td><td>${w.Rate}</td>`;
                
                for(let i=0; i<7; i++) {
                    row += `<td>${daysArr[i] || ""}</td>`;
                }

                row += `
                    <td>${dayCount}</td><td>${formatMoney(weekTotal)}</td>
                    <td>${formatMoney(w.Arrears)}</td><td>${formatMoney(totalDue)}</td>
                    <td>${formatMoney(w.Paid)}</td><td>${formatMoney(balance)}</td>
                </tr>`;
                
                if(tables[w.Type]) tables[w.Type].innerHTML += row;
            });

            document.getElementById("sumArrears").innerText = formatMoney(totals.arrears);
            document.getElementById("sumPaid").innerText = formatMoney(totals.paid);
            document.getElementById("sumBalance").innerText = formatMoney(totals.balance);
        }

        window.onload = loadData;
    </script>
</body>
</html>
