# js-persistent-cookie-demo
A simple HTML and JavaScript example for setting a persistent cookie.


In your newly created repository, click on the Add file button and select Create new file.
Name your file index.html.
Copy and paste your code into the editor:

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>Persistent Cookie</h2>
    <input type="text" id="nameInput" placeholder="Enter Name">
    <button onclick="setCookie()">Set Cookie</button>

    <script>
        function setCookie() {
            const name = document.getElementById("nameInput").value.trim();
            if (name === "") {
                alert("Enter Name");
                return;
            }
            const expireDate = new Date();
            expireDate.setFullYear(expireDate.getFullYear() + 1);
            document.cookie = `user_name=${encodeURIComponent(name)}; expires=${expireDate.toUTCString()}; path=/`;
            alert(`Persistent cookie 'user_name' set with value: ${name}`);
        }
    </script>
</body>
</html>

