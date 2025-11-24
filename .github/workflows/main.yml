<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KEOSS - Calculadora de Financiamiento</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: #667eea;
            color: #333;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 1100px;
            width: 100%;
            background-color: white;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }
        
        header {
            background: #ff6b6b;
            color: white;
            padding: 30px;
            text-align: center;
            position: relative;
        }
        
        .logo {
            font-size: 3.5rem;
            font-weight: bold;
            margin-bottom: 10px;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.95;
            font-weight: 500;
        }
        
        .content {
            padding: 35px;
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
        }
        
        .calculator {
            flex: 1;
            min-width: 320px;
            background: #f5576c;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            color: white;
        }
        
        .input-group {
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            font-size: 1.1rem;
        }
        
        input {
            width: 100%;
            padding: 14px 18px;
            border: 2px solid rgba(255,255,255,0.3);
            border-radius: 10px;
            font-size: 16px;
            transition: all 0.3s;
            background: rgba(255,255,255,0.9);
        }
        
        input:focus {
            border-color: white;
            outline: none;
            background: white;
            transform: scale(1.02);
        }
        
        button {
            background: #4facfe;
            color: white;
            border: none;
            padding: 16px 20px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 18px;
            font-weight: 700;
            width: 100%;
            transition: transform 0.3s, box-shadow 0.3s;
            margin-top: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        button:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(79, 172, 254, 0.5);
            background: #3a9df7;
        }
        
        .results {
            flex: 1;
            min-width: 320px;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .result-card {
            background-color: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            border: 3px solid;
        }
        
        .result-card:hover {
            transform: translateY(-8px);
        }
        
        .total-card {
            border-color: #4cd964;
            background: #96e6a1;
        }
        
        .initial-card {
            border-color: #5ac8fa;
            background: #c2e9fb;
        }
        
        .financed-card {
            border-color: #ff9500;
            background: #fcb69f;
        }
        
        .result-card h3 {
            margin-bottom: 15px;
            font-size: 1.4rem;
            display: flex;
            align-items: center;
        }
        
        .total-card h3 {
            color: #2c7744;
        }
        
        .initial-card h3 {
            color: #1a6ea0;
        }
        
        .financed-card h3 {
            color: #cc5c29;
        }
        
        .result-value {
            font-size: 2rem;
            font-weight: bold;
            text-align: center;
            margin: 15px 0;
        }
        
        .total-value {
            color: #2c7744;
        }
        
        .initial-value {
            color: #1a6ea0;
        }
        
        .financed-value {
            color: #cc5c29;
        }
        
        .result-detail {
            color: #555;
            margin-top: 10px;
            text-align: center;
            font-weight: 500;
        }
        
        .cuotas {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            gap: 10px;
        }
        
        .cuota {
            flex: 1;
            text-align: center;
            padding: 10px;
            background: rgba(255,255,255,0.7);
            border-radius: 8px;
            font-weight: bold;
        }
        
        .examples {
            width: 100%;
            margin-top: 30px;
        }
        
        h2 {
            color: #ff6b6b;
            margin-bottom: 20px;
            font-size: 1.8rem;
            border-bottom: 3px solid #ff6b6b;
            padding-bottom: 10px;
            text-align: center;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            border-radius: 12px;
            overflow: hidden;
        }
        
        th, td {
            padding: 15px;
            text-align: center;
            border-bottom: 1px solid #dee2e6;
        }
        
        th {
            background: #ff6b6b;
            color: white;
            font-size: 1.1rem;
        }
        
        tr:nth-child(even) {
            background-color: #f8f9fa;
        }
        
        tr:hover {
            background-color: #e9ecef;
            transform: scale(1.01);
            transition: transform 0.2s;
        }
        
        .formula {
            font-style: italic;
            color: rgba(255,255,255,0.9);
            margin-top: 15px;
            text-align: center;
            padding: 12px;
            background: rgba(0,0,0,0.1);
            border-radius: 8px;
            border-left: 4px solid white;
            font-weight: 500;
        }
        
        footer {
            text-align: center;
            padding: 25px;
            color: #6c757d;
            font-size: 1rem;
            border-top: 1px solid #e9ecef;
            background-color: #f8f9fa;
        }
        
        @media (max-width: 768px) {
            .content {
                flex-direction: column;
            }
            
            .container {
                border-radius: 15px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .content {
                padding: 25px;
            }
            
            th, td {
                padding: 10px 12px;
            }
            
            .logo {
                font-size: 2.8rem;
            }
        }
        
        .percentage-input, .amount-input {
            position: relative;
        }
        
        .percentage-input:after {
            content: "%";
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: #666;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .amount-input:before {
            content: "$";
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: #666;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .amount-input input {
            padding-left: 35px;
        }
        
        .icon {
            margin-right: 12px;
            font-size: 1.8rem;
        }
        
        .cuota-number {
            font-weight: bold;
            color: #ff6b6b;
        }
        
        .cuota-amount {
            font-weight: bold;
            color: #2c7744;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">KEOSS</div>
            <h1>Calculadora de Financiamiento</h1>
            <p class="subtitle">Calcula el valor total y pago inicial con un monto financiado personalizable</p>
        </header>
        
        <div class="content">
            <div class="calculator">
                <div class="input-group">
                    <label for="initial-percentage">Porcentaje de pago inicial:</label>
                    <div class="percentage-input">
                        <input type="number" id="initial-percentage" placeholder="Ejemplo: 40" min="0" max="100" step="0.01">
                    </div>
                </div>
                
                <div class="input-group">
                    <label for="financed-amount">Monto financiado:</label>
                    <div class="amount-input">
                        <input type="number" id="financed-amount" value="120" min="0" step="0.01">
                    </div>
                </div>
                
                <button id="calculate">Calcular Financiamiento</button>
                
                <div class="formula">
                    Fórmula: Valor Total = Monto Financiado / (1 - Porcentaje Inicial/100)
                </div>
            </div>
            
            <div class="results">
                <div class="result-card total-card">
                    <h3><span class="icon">💰</span> Monto por generar en CASHEA</h3>
                    <div class="result-value total-value" id="total-value">$0.00</div>
                    <div class="result-detail">Este es el 100% del valor del producto</div>
                </div>
                
                <div class="result-card initial-card">
                    <h3><span class="icon">💵</span> Pago Inicial CASHEA (No se paga)</h3>
                    <div class="result-value initial-value" id="initial-payment">$0.00</div>
                    <div class="result-detail" id="initial-percentage-display">-</div>
                </div>
                
                <div class="result-card financed-card">
                    <h3><span class="icon">📈</span> Monto financiado por CASHEA</h3>
                    <div class="result-value financed-value" id="financed-display">$0.00</div>
                    <div class="result-detail" id="financed-percentage-display">-</div>
                    <div class="cuotas" id="cuotas-container">
                        <!-- Las cuotas se generarán aquí -->
                    </div>
                </div>
            </div>
            
            <div class="examples">
                <h2>Ejemplos de Cálculo:</h2>
                <table>
                    <thead>
                        <tr>
                            <th>Pago Inicial</th>
                            <th>Monto Financiado</th>
                            <th>Valor Total</th>
                            <th>Cuotas CASHEA</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>40%</td>
                            <td>$120.00</td>
                            <td>$200.00</td>
                            <td>3 cuotas de $40.00</td>
                        </tr>
                        <tr>
                            <td>50%</td>
                            <td>$120.00</td>
                            <td>$240.00</td>
                            <td>3 cuotas de $40.00</td>
                        </tr>
                        <tr>
                            <td>60%</td>
                            <td>$120.00</td>
                            <td>$300.00</td>
                            <td>3 cuotas de $40.00</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
        
        <footer>
            <p>KEOSS - Calculadora de financiamiento inteligente | Compatible con GitHub Pages</p>
        </footer>
    </div>

    <script>
        document.getElementById('calculate').addEventListener('click', calculateFinancing);
        document.getElementById('initial-percentage').addEventListener('keyup', function(event) {
            if (event.key === 'Enter') {
                calculateFinancing();
            }
        });
        
        document.getElementById('financed-amount').addEventListener('keyup', function(event) {
            if (event.key === 'Enter') {
                calculateFinancing();
            }
        });
        
        // Calcular automáticamente cuando cambian los valores
        document.getElementById('initial-percentage').addEventListener('input', calculateFinancing);
        document.getElementById('financed-amount').addEventListener('input', calculateFinancing);
        
        function calculateFinancing() {
            const initialPercentage = parseFloat(document.getElementById('initial-percentage').value);
            const financedAmount = parseFloat(document.getElementById('financed-amount').value);
            
            // Validaciones
            if (isNaN(initialPercentage) || initialPercentage < 0 || initialPercentage >= 100) {
                document.getElementById('total-value').textContent = '$0.00';
                document.getElementById('initial-payment').textContent = '$0.00';
                document.getElementById('financed-display').textContent = '$0.00';
                document.getElementById('initial-percentage-display').textContent = 'Ingrese un porcentaje válido (0-99.99)';
                document.getElementById('financed-percentage-display').textContent = '-';
                document.getElementById('cuotas-container').innerHTML = '';
                return;
            }
            
            if (isNaN(financedAmount) || financedAmount <= 0) {
                document.getElementById('total-value').textContent = '$0.00';
                document.getElementById('initial-payment').textContent = '$0.00';
                document.getElementById('financed-display').textContent = '$0.00';
                document.getElementById('initial-percentage-display').textContent = '-';
                document.getElementById('financed-percentage-display').textContent = 'Ingrese un monto válido';
                document.getElementById('cuotas-container').innerHTML = '';
                return;
            }
            
            // Calcular el valor total
            const totalValue = financedAmount / (1 - initialPercentage/100);
            
            // Calcular el pago inicial
            const initialPayment = totalValue * (initialPercentage/100);
            
            // Calcular el porcentaje financiado
            const financedPercentage = 100 - initialPercentage;
            
            // Calcular cuotas (dividir en 3)
            const cuotaAmount = financedAmount / 3;
            
            // Mostrar resultados
            document.getElementById('total-value').textContent = `$${totalValue.toFixed(2)}`;
            document.getElementById('initial-payment').textContent = `$${initialPayment.toFixed(2)}`;
            document.getElementById('financed-display').textContent = `$${financedAmount.toFixed(2)}`;
            document.getElementById('initial-percentage-display').textContent = 
                `Equivale al ${initialPercentage.toFixed(2)}% del valor total`;
            document.getElementById('financed-percentage-display').textContent = 
                `Equivale al ${financedPercentage.toFixed(2)}% del valor total`;
                
            // Mostrar cuotas
            const cuotasContainer = document.getElementById('cuotas-container');
            cuotasContainer.innerHTML = `
                <div class="cuota">
                    <div class="cuota-number">Cuota 1</div>
                    <div class="cuota-amount">$${cuotaAmount.toFixed(2)}</div>
                </div>
                <div class="cuota">
                    <div class="cuota-number">Cuota 2</div>
                    <div class="cuota-amount">$${cuotaAmount.toFixed(2)}</div>
                </div>
                <div class="cuota">
                    <div class="cuota-number">Cuota 3</div>
                    <div class="cuota-amount">$${cuotaAmount.toFixed(2)}</div>
                </div>
            `;
        }
        
        // Calcular automáticamente al cargar la página con un ejemplo
        window.addEventListener('load', function() {
            document.getElementById('initial-percentage').value = '40';
            calculateFinancing();
        });
    </script>
</body>
</html>
