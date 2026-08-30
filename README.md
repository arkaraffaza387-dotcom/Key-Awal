<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AzferFree - Get Key</title>

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
        font-family: Arial, sans-serif;
    }

    body {
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        background:
            radial-gradient(circle at top, #182848, #050505 55%);
        color: white;
        padding: 20px;
    }

    .container {
        width: 100%;
        max-width: 430px;
        padding: 30px;
        border: 1px solid #00eaff;
        border-radius: 20px;
        background: rgba(10, 10, 20, 0.88);
        box-shadow:
            0 0 20px rgba(0, 234, 255, .25),
            inset 0 0 25px rgba(0, 234, 255, .05);
        text-align: center;
    }

    .logo {
        font-size: 32px;
        font-weight: bold;
        color: #00eaff;
        text-shadow: 0 0 15px #00eaff;
        margin-bottom: 8px;
    }

    .subtitle {
        color: #aaa;
        font-size: 14px;
        margin-bottom: 28px;
    }

    .key-box {
        background: #050505;
        border: 1px solid #333;
        border-radius: 12px;
        padding: 15px;
        margin-bottom: 15px;
        word-break: break-all;
        color: #00ff9d;
        font-size: 14px;
        box-shadow: inset 0 0 15px rgba(0,255,157,.05);
    }

    .key-label {
        display: block;
        color: #777;
        font-size: 11px;
        margin-bottom: 8px;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    button {
        width: 100%;
        border: none;
        padding: 14px;
        border-radius: 10px;
        font-size: 15px;
        font-weight: bold;
        cursor: pointer;
        transition: .2s;
    }

    .copy-btn {
        background: #00eaff;
        color: #001014;
        margin-bottom: 15px;
    }

    .copy-btn:hover {
        box-shadow: 0 0 18px #00eaff;
        transform: translateY(-2px);
    }

    .get-btn {
        background: transparent;
        color: #00ff9d;
        border: 1px solid #00ff9d;
    }

    .get-btn:hover {
        background: #00ff9d;
        color: #00100a;
        box-shadow: 0 0 18px #00ff9d;
        transform: translateY(-2px);
    }

    .status {
        min-height: 20px;
        margin-top: 15px;
        color: #888;
        font-size: 12px;
    }

    .footer {
        margin-top: 25px;
        color: #555;
        font-size: 11px;
    }
</style>
</head>

<body>

<div class="container">

    <div class="logo">AZFER FREE</div>

    <div class="subtitle">
        Key Generator System
    </div>

    <div class="key-box">
        <span class="key-label">Your Key</span>
        <span id="key">Generating...</span>
    </div>

    <button class="copy-btn" onclick="copyKey()">
        📋 SALIN KEY
    </button>

    <button class="get-btn" onclick="getKey()">
        Click For Get Key
    </button>

    <div class="status" id="status"></div>

    <div class="footer">
        AzferFree Key System © 2026
    </div>

</div>

<script>
    const characters =
        "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";

    function generateKey() {
        let randomPart = "";

        for (let i = 0; i < 23; i++) {
            randomPart += characters.charAt(
                Math.floor(Math.random() * characters.length)
            );
        }

        return "AzferFree_" + randomPart;
    }

    let currentKey = generateKey();

    document.getElementById("key").textContent = currentKey;

    function copyKey() {
        navigator.clipboard.writeText(currentKey).then(() => {
            document.getElementById("status").textContent =
                "✓ Key berhasil disalin!";
        }).catch(() => {
            document.getElementById("status").textContent =
                "Gagal menyalin key.";
        });
    }

    function getKey() {
        window.location.href =
            "https://arkaraffaza387-dotcom.github.io/Key-Zero/";
    }
</script>

</body>
</html>
