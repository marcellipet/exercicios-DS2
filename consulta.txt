<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "biblioteca;"

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Conexão falhou: " . $conn->connect_error);
}

$sql = "SELECT titulo, autor FROM livros";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    echo "<table>";
    echo "<tr><th>Título</th><th>Autor</th></tr>";

    while($row = $resul->fetch_assoc()) {
        echo "<tr><td>" . $row["titulo"]. "</td><td>" . $row["autor"]. "</td></tr>";
    }
    echo "</table>";
} else {
    echo "Nenhum livro encontrado."
}