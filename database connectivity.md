



## Database Connectivity methods.

<table>
  <thead>
    <tr>
      <th>Function / Method</th>
      <th>Syntax</th>
      <th>Description + Example + Output</th>
    </tr>
  </thead>
  <tbody>
    <tr><th colspan="3">MySQLi (Procedural) – Connection Functions</th></tr>
    <tr>
      <td>mysqli_connect()</td>
      <td><code>mysqli_connect(host, user, pass, db)</code></td>
      <td>Opens a connection to MySQL database.<br>
      Example:<br><code>$con = mysqli_connect("localhost","root","","test");</code><br>Output: connection object OR false</td>
    </tr>
    <tr>
      <td>mysqli_connect_errno()</td>
      <td><code>mysqli_connect_errno()</code></td>
      <td>Returns error number if connection failed.<br>
      Example:<br><code>mysqli_connect_errno();</code><br>Output: <code>1045</code> (example)</td>
    </tr>
    <tr>
      <td>mysqli_connect_error()</td>
      <td><code>mysqli_connect_error()</code></td>
      <td>Returns error message for connection failure.<br>
      Example:<br><code>mysqli_connect_error();</code><br>Output: <code>Access denied for user...</code></td>
    </tr>
    <tr><th colspan="3">MySQLi (Procedural) – Query & Fetch Methods</th></tr>
    <tr>
      <td>mysqli_query()</td>
      <td><code>mysqli_query(connection, query)</code></td>
      <td>Executes an SQL query (SELECT/INSERT/UPDATE/DELETE).<br>
      Example:<br><code>$result = mysqli_query($con,"SELECT * FROM users");</code><br>Output: result object OR true/false</td>
    </tr>
    <tr>
      <td>mysqli_fetch_assoc()</td>
      <td><code>mysqli_fetch_assoc(result)</code></td>
      <td>Fetches row as associative array.<br>
      Example:<br><code>$row = mysqli_fetch_assoc($result);</code><br>Output: <code>["id"=>1,"name"=>"Shivam"]</code></td>
    </tr>
    <tr>
      <td>mysqli_fetch_row()</td>
      <td><code>mysqli_fetch_row(result)</code></td>
      <td>Fetches row as numeric array.<br>
      Example:<br><code>$row = mysqli_fetch_row($result);</code><br>Output: <code>[1,"Shivam"]</code></td>
    </tr>
    <tr>
      <td>mysqli_fetch_array()</td>
      <td><code>mysqli_fetch_array(result, type)</code></td>
      <td>Fetches row as associative + numeric array.<br>
      Example:<br><code>$row = mysqli_fetch_array($result);</code><br>Output: <code>["id"=>1,0=>1,"name"=>"Shivam",1=>"Shivam"]</code></td>
    </tr>
    <tr>
      <td>mysqli_num_rows()</td>
      <td><code>mysqli_num_rows(result)</code></td>
      <td>Returns number of rows in result set.<br>
      Example:<br><code>mysqli_num_rows($result);</code><br>Output: <code>5</code></td>
    </tr>
    <tr>
      <td>mysqli_affected_rows()</td>
      <td><code>mysqli_affected_rows(connection)</code></td>
      <td>Returns affected rows for INSERT/UPDATE/DELETE.<br>
      Example:<br><code>mysqli_affected_rows($con);</code><br>Output: <code>1</code></td>
    </tr>
    <tr>
      <td>mysqli_real_escape_string()</td>
      <td><code>mysqli_real_escape_string(connection, string)</code></td>
      <td>Escapes special characters to prevent SQL Injection.<br>
      Example:<br><code>$safe = mysqli_real_escape_string($con,$input);</code></td>
    </tr>
    <tr>
      <td>mysqli_close()</td>
      <td><code>mysqli_close(connection)</code></td>
      <td>Closes MySQL connection.<br>
      Example:<br><code>mysqli_close($con);</code></td>
    </tr>
    <tr><th colspan="3">MySQLi (OOP Style)</th></tr>
    <tr>
      <td>new mysqli()</td>
      <td><code>$db = new mysqli(host,user,pass,db)</code></td>
      <td>Opens a database connection (OOP way).<br>
      Example:<br><code>$db = new mysqli("localhost","root","","shop");</code></td>
    </tr>
    <tr>
      <td>$db->query()</td>
      <td><code>$db->query(sql)</code></td>
      <td>Executes SQL query.<br>
      Example:<br><code>$res = $db->query("SELECT * FROM users");</code></td>
    </tr>
    <tr>
      <td>$result->fetch_assoc()</td>
      <td><code>$result->fetch_assoc()</code></td>
      <td>Fetches row as associative array.<br>
      Example:<br><code>$row = $res->fetch_assoc();</code></td>
    </tr>
    <tr>
      <td>$db->prepare()</td>
      <td><code>$stmt = $db->prepare(sql)</code></td>
      <td>Creates prepared statements (secure against SQL injection).<br>
      Example:<br><code>$stmt = $db->prepare("SELECT * FROM users WHERE id=?");</code></td>
    </tr>
    <tr>
      <td>$stmt->bind_param()</td>
      <td><code>$stmt->bind_param("i", $id)</code></td>
      <td>Binds variables to prepared statement.<br>
      Example:<br><code>$stmt->bind_param("s",$name);</code></td>
    </tr>
    <tr>
      <td>$stmt->execute()</td>
      <td><code>$stmt->execute()</code></td>
      <td>Executes prepared statement.<br>
      Example:<br><code>$stmt->execute();</code></td>
    </tr>
    <tr>
      <td>$stmt->get_result()</td>
      <td><code>$stmt->get_result()</code></td>
      <td>Gets result object from prepared query.<br>
      Example:<br><code>$res = $stmt->get_result();</code></td>
    </tr>
    <tr>
      <td>$db->close()</td>
      <td><code>$db->close()</code></td>
      <td>Closes database connection.</td>
    </tr>
    <tr><th colspan="3">PDO (PHP Data Objects) – Recommended Modern Method</th></tr>
    <tr>
      <td>new PDO()</td>
      <td><code>$pdo = new PDO(dsn, user, pass, options)</code></td>
      <td>Creates a secure database connection supporting many DB types.<br>
      Example:<br><code>$pdo = new PDO("mysql:host=localhost;dbname=test","root","");</code></td>
    </tr>
    <tr>
      <td>$pdo->setAttribute()</td>
      <td><code>$pdo->setAttribute(const,value)</code></td>
      <td>Sets PDO behavior (error mode, fetch mode).<br>
      Example:<br><code>$pdo->setAttribute(PDO::ATTR_ERRMODE,PDO::ERRMODE_EXCEPTION);</code></td>
    </tr>
    <tr>
      <td>$pdo->query()</td>
      <td><code>$pdo->query(sql)</code></td>
      <td>Executes a direct SQL query.<br>
      Example:<br><code>$result = $pdo->query("SELECT * FROM users");</code></td>
    </tr>
    <tr>
      <td>$pdo->prepare()</td>
      <td><code>$stmt = $pdo->prepare(sql)</code></td>
      <td>Prepares an SQL query (safe & secure).<br>
      Example:<br><code>$stmt = $pdo->prepare("SELECT * FROM users WHERE id=?");</code></td>
    </tr>
    <tr>
      <td>$stmt->execute()</td>
      <td><code>$stmt->execute([values])</code></td>
      <td>Executes prepared statement with array of values.<br>
      Example:<br><code>$stmt->execute([5]);</code></td>
    </tr>
    <tr>
      <td>$stmt->fetch()</td>
      <td><code>$stmt->fetch(PDO::FETCH_ASSOC)</code></td>
      <td>Fetches single row.<br>
      Example:<br><code>$row = $stmt->fetch();</code></td>
    </tr>
    <tr>
      <td>$stmt->fetchAll()</td>
      <td><code>$stmt->fetchAll(PDO::FETCH_ASSOC)</code></td>
      <td>Fetches all rows from query.<br>
      Example:<br><code>$rows = $stmt->fetchAll();</code></td>
    </tr>
    <tr>
      <td>$pdo->lastInsertId()</td>
      <td><code>$pdo->lastInsertId()</code></td>
      <td>Returns ID of last inserted row.<br>
      Example:<br><code>$id = $pdo->lastInsertId();</code><br>Output: <code>17</code></td>
    </tr>
    <tr>
      <td>$pdo->beginTransaction()</td>
      <td><code>$pdo->beginTransaction()</code></td>
      <td>Starts a SQL transaction.<br>
      Example:<br><code>$pdo->beginTransaction();</code></td>
    </tr>
    <tr>
      <td>$pdo->commit()</td>
      <td><code>$pdo->commit()</code></td>
      <td>Commits the transaction.<br>
      Example:<br><code>$pdo->commit();</code></td>
    </tr>
    <tr>
      <td>$pdo->rollBack()</td>
      <td><code>$pdo->rollBack()</code></td>
      <td>Rolls back transaction (undo changes).<br>
      Example:<br><code>$pdo->rollBack();</code></td>
    </tr>
  </tbody>
</table>
