<!DOCTYPE html>
<html>
<head>
    <title>Table with Rows and Columns</title>
    <style>
        table, td {
            border: 1px solid rgb(185, 57, 57);
            border-collapse: collapse;
            padding: 8px;
            border-width: 10px;
        }
    </style>
</head>
<body>
    <table id="myTable">
        <tr><td>Row1 Col1</td><td>Row1 Col2</td></tr>
        <tr><td>Row2 Col1</td><td>Row2 Col2</td></tr>
        <tr><td>Row3 Col1</td><td>Row3 Col2</td></tr>
        <tr><td>Row4 Col1</td><td>Row4 Col2</td></tr>
        <tr><td>Row5 Col1</td><td>Row5 Col2</td></tr>
    </table>
    
    <br>

    <button onclick="insertRow()">Insert</button>
    <button onclick="removeRow()">Remove</button>

    <p id="message"></p>

    <script>
        var rowCount = 6; // Start from 6 since 5 rows already exist

        function insertRow() {
            var table = document.getElementById("myTable");
            var newRow = table.insertRow();
            newRow.innerHTML = '<td>Row' + rowCount + ' Col1</td><td>Row' + rowCount + ' Col2</td>';
            rowCount++;
            
            document.getElementById("message").innerHTML = "";
        }

        function removeRow() {
            var table = document.getElementById("myTable");
            var messageElement = document.getElementById("message");

            if (table.rows.length > 0) {
                table.deleteRow(0);
                messageElement.innerHTML = "";
            } else {
                messageElement.innerHTML = "Message: Nothing exists to delete more";
            }
        }
    </script>
</body>
</html>
