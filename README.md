# web-expense-Tracker
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expense Tracker</title>

    <style>
        body{
            font-family: Arial, Helvetica, sans-serif;
            background-color: rgb(190, 199, 199);
            margin-top: 8%;
            
        }
        .container{
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: rgb(222, 230, 236);
            border-radius: 8px;
            box-shadow: 0 10px 10px rgba(17, 1, 1, 0.1);
            display: grid;
            align-items: center;
            
        }
        input[type="text"],select,input[type=number],input[type=submit]
        {
            margin-bottom: 10px;
            width: 100%;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;

        }         
        input[type="submit"]{
            background-color: green;
            color: aliceblue;
            border: none;
            cursor: pointer;

        }
        input[type="submit"]:hover
        {
    background-color: green;
        }
        table{
            border-collapse: collapse;
        }
        th,td{
            border: 1px solid#ddd;
            padding: 8px;
            text-align: left;

        }
        th{
            background-color: green;
            color: white;
        }
        
        
           </style>
</head>
<body>
    <div class="container">
        <h2>Expense Tracker</h2>
    <form id="Expenseform">
        <input type="text" id="description" placeholder="expense description" required/><br>
        <select  id="category" required>
            <option value="category">select category</option>
        <option value="Food">Food</option>
    <option value="transportation">transportation</option>        
<option value="Entertainment">Entertainment</option>
<option value="others">others</option>
</select><br>
<input type="number" id="amount" placeholder="amount" required><br>
<input type="submit"value="Add Expense">

    </form>
    <h3>Expense summary</h3>
    <table id = "ExpensiveTable">
        <thead>
            <tr>
                <th>Description</th>
                <th>category</th>
                <th>Amount</th>
            </tr>
        </thead>
        <tbody id="expenselist"></tbody>
    </table>
    </div>
    
    
<script>
 const expenseform = document.getElementById('Expenseform');
    const expenselist = document.getElementById('expenselist');
    expenseform.addEventListener('submit', function (event) {
        event.preventDefault();

        const description = document.getElementById('description').value;
        const category = document.getElementById('category').value;
        const amount = document.getElementById('amount').value;
        if (description && category && !isNaN(amount)) {
            const newrow = document.createElement('tr')
            newrow.innerHTML = `<td>${description}</td>
    <td>${category}</td>
    <td>${amount}</td>`;
            expenselist.appendChild(newrow)
            document.getElementById('description').value = ''
            document.getElementById('category').value = ''
            document.getElementById('amount').value = ''



        }
        else {
            alert('please fill out al fields with valid data')
        }
    })
</script>
</body>

</html>
