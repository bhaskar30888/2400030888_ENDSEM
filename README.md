<!DOCTYPE html>
<html>
<head>
    <title>Student Attendance Tracker</title>
    <style>
        table {
            width: 70%;
            border-collapse: collapse;
            margin: 20px auto;
            font-family: Arial, sans-serif;
        }
        th, td {
            border: 1px solid #333;
            padding: 10px;
            text-align: center;
        }
        th {
            background-color: #f2f2f2;
        }
        caption {
            font-size: 1.5em;
            margin-bottom: 10px;
            font-weight: bold;
        }
        .present {
            color: green;
            font-weight: bold;
        }
        .absent {
            color: red;
            font-weight: bold;
        }
    </style>
</head>
<body>

<table>
    <caption>Student Attendance</caption>
    <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Status</th>
    </tr>

    <tr>
        <td>1</td>
        <td>Bhaskar</td>
        <td class="absent">Absent</td>
    </tr>

    <tr>
        <td>2</td>
        <td>Raju</td>
        <td class="absent">Absent</td>
    </tr>

    <tr>
        <td>3</td>
        <td>Harsha</td>
        <td class="present">Present</td>
    </tr>

</table>

</body>
</html>
