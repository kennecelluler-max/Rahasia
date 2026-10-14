<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halaman Rahasia</title>
    
    <!-- Tag untuk mengusir AI dan Mesin Pencari -->
    <meta name="robots" content="noindex, nofollow">
    <meta name="GPTBot" content="noindex, nofollow">
    <meta name="ClaudeBot" content="no-index">
    
    <style>
        body { font-family: Arial, sans-serif; background-color: #f4f4f9; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
        .container { background: white; padding: 40px; border-radius: 10px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); text-align: center; max-width: 400px; width: 100%; }
        h2 { color: #333; }
        input { padding: 10px; width: 80%; margin-bottom: 15px; border: 1px solid #ccc; border-radius: 5px; }
        button { padding: 10px 20px; background-color: #007bff; color: white; border: none; border-radius: 5px; cursor: pointer; font-size: 16px; }
        button:hover { background-color: #0056b3; }
        #error { color: red; display: none; margin-top: 10px; }
        #locked-content { display: none; }
        #locked-content h1 { color: #28a745; }
    </style>
</head>
<body>

    <!-- Layar Password -->
    <div id="password-prompt" class="container">
        <h2>🔒 Area Terkunci</h2>
        <p>Masukkan password untuk melanjutkan:</p>
        <input type="password" id="passInput" placeholder="Password...">
        <br>
        <button onclick="checkPass()">Buka</button>
        <p id="error">Password salah! Coba lagi.</p>
    </div>

    <!-- Konten Rahasia (Hanya muncul jika password benar) -->
    <div id="locked-content" class="container">
        <h1>Selamat Datang!</h1>
        <p>Ini adalah konten rahasia Anda. AI dan bot tidak bisa membacanya karena terhalang password.</p>
        <p>Silakan tulis konten rahasia Anda di sini.</p>
    </div>

    <script>
        function checkPass() {
            // Ganti 'senyum' dengan password pilihan Anda
            const passwordBenar = 'rahasia123'; 
            const input = document.getElementById('passInput').value;
            
            if (input === passwordBenar) {
                document.getElementById('password-prompt').style.display = 'none';
                document.getElementById('locked-content').style.display = 'block';
            } else {
                document.getElementById('error').style.display = 'block';
            }
        }
        
        // Memungkinkan menekan tombol "Enter" pada keyboard untuk login
        document.getElementById('passInput').addEventListener("keypress", function(event) {
            if (event.key === "Enter") { checkPass(); }
        });
    </script>
</body>
</html>
