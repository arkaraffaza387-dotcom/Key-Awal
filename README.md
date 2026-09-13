<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🔑 Create Key • AzferModz</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;800;900&family=Orbitron:wght@700;900&display=swap" rel="stylesheet">
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
<style>
* { margin:0; padding:0; box-sizing:border-box; font-family:'Poppins',sans-serif; -webkit-tap-highlight-color: transparent; }

body {
    background: radial-gradient(ellipse at center, #1a0000 0%, #0a0000 50%, #000000 100%);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 16px;
    color: #fff;
    position: relative;
    overflow-x: hidden;
}
body::before {
    content: "";
    position: fixed;
    inset: 0;
    background:
        radial-gradient(circle at 20% 20%, rgba(139, 0, 0, 0.3) 0%, transparent 50%),
        radial-gradient(circle at 80% 80%, rgba(184, 134, 11, 0.2) 0%, transparent 50%),
        radial-gradient(circle at 50% 50%, rgba(255, 215, 0, 0.05) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
}

.card {
    background: linear-gradient(165deg, #1a0a0a 0%, #0d0505 30%, #1a0a0a 70%, #0a0000 100%);
    border: 2px solid #b8860b;
    border-radius: 40px;
    box-shadow: 0 30px 60px -12px rgba(139, 0, 0, 0.8),
                0 0 0 1px rgba(255, 215, 0, 0.3) inset,
                0 0 30px rgba(184, 134, 11, 0.3);
    width: 100%;
    max-width: 480px;
    padding: 40px 28px;
    position: relative;
    z-index: 1;
    animation: fadeIn 0.8s ease;
}
@keyframes fadeIn { from { opacity:0; transform:scale(0.95); } to { opacity:1; transform:scale(1); } }

.card::before {
    content: "";
    position: absolute;
    top: -2px;
    left: 20%;
    right: 20%;
    height: 3px;
    background: linear-gradient(90deg, transparent, #ffed4a, #ffd700, #ffed4a, transparent);
    border-radius: 50%;
    filter: blur(1px);
    animation: shine 3s ease-in-out infinite;
}
@keyframes shine {
    0%,100% { opacity:0.5; transform:scaleX(0.8); }
    50% { opacity:1; transform:scaleX(1); }
}

.title {
    text-align: center;
    font-size: 1.9rem;
    font-weight: 900;
    background: linear-gradient(135deg, #ffd700 0%, #ffed4a 30%, #b8860b 60%, #ffd700 100%);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}
.subtitle {
    text-align: center;
    color: #cc9999;
    font-size: 0.88rem;
    margin-bottom: 26px;
    letter-spacing: 1px;
}

.alert {
    padding: 12px 16px;
    border-radius: 12px;
    font-size: 13px;
    margin-bottom: 16px;
    display: none;
    line-height: 1.5;
    animation: fadeIn 0.3s ease;
}
.alert.show { display: block; }
.alert-info { background: rgba(100,150,255,0.12); border: 1px solid rgba(100,150,255,0.4); color: #a0c0ff; }
.alert-error { background: rgba(255,50,50,0.12); border: 1px solid rgba(255,50,50,0.4); color: #ff9999; }
.alert-success { background: rgba(50,255,100,0.12); border: 1px solid rgba(50,255,100,0.4); color: #99ff99; }

.btn {
    padding: 15px 24px;
    border: none;
    border-radius: 60px;
    font-family: 'Poppins', sans-serif;
    font-size: 14px;
    font-weight: 800;
    cursor: pointer;
    letter-spacing: 1.2px;
    text-transform: uppercase;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    transition: all 0.3s ease;
    width: 100%;
    position: relative;
    overflow: hidden;
}
.btn-primary {
    background: linear-gradient(135deg, #8b0000 0%, #cc0000 50%, #8b0000 100%);
    border: 2px solid #ffd700;
    color: #ffed4a;
    box-shadow: 0 12px 30px -5px rgba(139, 0, 0, 0.8), 0 0 20px rgba(255, 215, 0, 0.2);
}
.btn-primary:hover:not(:disabled) {
    transform: scale(1.02);
    background: linear-gradient(135deg, #cc0000 0%, #ff1a1a 50%, #cc0000 100%);
    box-shadow: 0 18px 40px -6px rgba(204, 0, 0, 0.9), 0 0 40px rgba(255, 215, 0, 0.4);
}
.btn-primary:active:not(:disabled) { transform: scale(0.98); }
.btn-primary:disabled { opacity: 0.5; cursor: not-allowed; }

.btn-secondary {
    background: rgba(255, 215, 0, 0.08);
    border: 1px solid rgba(255, 215, 0, 0.4);
    color: #ffd700;
    margin-top: 12px;
}
.btn-secondary:hover { background: rgba(255, 215, 0, 0.15); }

.key-display {
    background: linear-gradient(145deg, #1a0505 0%, #0d0202 100%);
    border: 2px solid #ffd700;
    border-radius: 30px;
    padding: 28px 20px;
    margin-top: 20px;
    position: relative;
    overflow: hidden;
    text-align: center;
    display: none;
    animation: keyAppear 0.6s ease-out;
    box-shadow: 0 0 40px rgba(255, 215, 0, 0.3), 0 0 60px rgba(139, 0, 0, 0.5);
}
@keyframes keyAppear {
    0% { transform: scale(0.8); opacity: 0; }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); opacity: 1; }
}
.key-display::before {
    content: "🔒 KEY ANDA";
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    background: #1a0a0a;
    color: #ffed4a;
    font-size: 0.65rem;
    font-weight: bold;
    letter-spacing: 2px;
    padding: 3px 16px;
    border-radius: 0 0 14px 14px;
    border: 1px solid #ffd700;
    border-top: none;
    text-transform: uppercase;
}

.key-value {
    font-family: 'Courier New', monospace;
    font-size: 1.4rem;
    font-weight: 800;
    color: #ffed4a;
    word-break: break-all;
    background: #0d0202;
    padding: 18px 12px;
    border-radius: 20px;
    letter-spacing: 1px;
    text-shadow: 0 0 15px rgba(255, 215, 0, 0.8), 0 0 30px rgba(255, 0, 0, 0.5);
    user-select: all;
    -webkit-user-select: all;
    margin-top: 14px;
    border: 1px solid #8b6914;
}

.timer-container {
    margin-top: 22px;
    padding: 18px;
    background: rgba(139, 0, 0, 0.15);
    border: 1px solid rgba(255, 68, 68, 0.4);
    border-radius: 20px;
    text-align: center;
}
.timer-label {
    font-size: 0.75rem;
    color: #cc9999;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 8px;
}
.timer-value {
    font-family: 'Orbitron', monospace;
    font-size: 2.6rem;
    font-weight: 900;
    background: linear-gradient(to bottom, #ffed4a 0%, #ffd700 40%, #b8860b 100%);
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    text-shadow: 0 0 40px rgba(255, 215, 0, 0.6);
    letter-spacing: 3px;
}
.timer-bar {
    margin-top: 12px;
    height: 8px;
    background: rgba(0,0,0,0.5);
    border-radius: 10px;
    overflow: hidden;
    border: 1px solid rgba(184, 134, 11, 0.5);
}
.timer-fill {
    height: 100%;
    background: linear-gradient(90deg, #8b0000, #ffd700);
    transition: width 1s linear;
    border-radius: 10px;
    box-shadow: 0 0 15px rgba(255, 215, 0, 0.5);
}
.timer-value.urgent {
    color: #ff4444;
    text-shadow: 0 0 40px rgba(255, 68, 68, 0.8);
}

.actions {
    display: flex;
    gap: 10px;
    margin-top: 16px;
}
.actions .btn { flex: 1; margin-top: 0; }

.history {
    margin-top: 24px;
    padding-top: 20px;
    border-top: 1px solid rgba(184, 134, 11, 0.3);
}
.history-title {
    font-size: 0.75rem;
    color: #cc9999;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 12px;
    text-align: center;
}
.history-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 14px;
    background: rgba(0,0,0,0.3);
    border-radius: 10px;
    margin-bottom: 6px;
    font-size: 11px;
    font-family: 'Courier New', monospace;
    border: 1px solid rgba(184, 134, 11, 0.2);
}
.history-item .key-text { color: #ffed4a; }
.history-item .time { color: #886666; }

.footer {
    text-align: center;
    margin-top: 24px;
    font-size: 0.75rem;
    color: #886666;
    letter-spacing: 1px;
}
</style>
</head>
<body>

<div class="card">
    <h1 class="title">🔑 CREATE KEY</h1>
    <p class="subtitle">Buat key akses kamu sendiri</p>

    <div class="alert alert-info" id="infoAlert">
        <strong>ℹ️ Info:</strong> Key berlaku <strong>3 menit</strong> sejak dibuat. Setelah expired, buat key baru.
    </div>

    <div class="alert alert-error" id="errorAlert"></div>
    <div class="alert alert-success" id="successAlert"></div>

    <button class="btn btn-primary" id="createBtn" onclick="createKey()">
        <i class="fas fa-magic"></i> BUAT KEY SEKARANG
    </button>

    <!-- KEY DISPLAY -->
    <div class="key-display" id="keyDisplay">
        <div class="key-value" id="keyValue">-</div>
        
        <div class="timer-container">
            <div class="timer-label">⏰ Sisa Waktu</div>
            <div class="timer-value" id="timerValue">03:00</div>
            <div class="timer-bar">
                <div class="timer-fill" id="timerFill" style="width: 100%;"></div>
            </div>
        </div>

        <div class="actions">
            <button class="btn btn-secondary" onclick="copyKey()" id="copyBtn">
                <i class="fas fa-copy"></i> SALIN
            </button>
            <button class="btn btn-secondary" onclick="resetKey()">
                <i class="fas fa-redo"></i> BARU
            </button>
        </div>
    </div>

    <!-- HISTORY -->
    <div class="history" id="historyBox" style="display:none;">
        <div class="history-title">📋 Riwayat Key (5 Terakhir)</div>
        <div id="historyList"></div>
    </div>

    <div class="footer">© 2025 AzferModz • Key Generator</div>
</div>

<script>
// ================================================================
// KONFIGURASI DATABASE
// ================================================================
const DB_API_KEY = "sk_34701ad7da358959a51880e914c5515d6947c583dc37cb90";
const DB_HOST = "https://free-database-fazxy.netlify.app";
const DB_BASE = DB_HOST + "/api/v1";
const COLLECTION = "keys";

// ================================================================
// KONFIGURASI KEY
// ================================================================
const KEY_PREFIX = "AzferFree_";
const KEY_RANDOM_LENGTH = 23;
const KEY_DURATION_MS = 3 * 60 * 1000; // 3 menit

// ================================================================
// STATE
// ================================================================
let currentKey = null;
let currentKeyId = null;
let timerInterval = null;
let keyStartTime = 0;

// ================================================================
// GENERATE KEY
// ================================================================
function generateKey() {
    const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    let random = "";
    for (let i = 0; i < KEY_RANDOM_LENGTH; i++) {
        random += chars.charAt(Math.floor(Math.random() * chars.length));
    }
    return KEY_PREFIX + random;
}

// ================================================================
// HISTORY
// ================================================================
function getKeyHistory() {
    try {
        return JSON.parse(localStorage.getItem('azfer_key_history') || '[]');
    } catch { return []; }
}

function addToHistory(key) {
    const history = getKeyHistory();
    history.unshift({ key, time: Date.now() });
    localStorage.setItem('azfer_key_history', JSON.stringify(history.slice(0, 5)));
    renderHistory();
}

function renderHistory() {
    const history = getKeyHistory();
    const box = document.getElementById('historyBox');
    const list = document.getElementById('historyList');
    if (!box || !list) return;
    if (history.length === 0) { box.style.display = 'none'; return; }
    box.style.display = 'block';
    list.innerHTML = history.map(h => {
        const timeAgo = Math.floor((Date.now() - h.time) / 1000);
        const mins = Math.floor(timeAgo / 60);
        const timeText = mins < 1 ? 'baru saja' : mins + ' menit lalu';
        return `<div class="history-item">
            <span class="key-text">${h.key.slice(0, 20)}...</span>
            <span class="time">${timeText}</span>
        </div>`;
    }).join('');
}

// ================================================================
// CREATE KEY — TANPA LIMIT
// ================================================================
async function createKey() {
    const btn = document.getElementById('createBtn');
    const errAlert = document.getElementById('errorAlert');
    const successAlert = document.getElementById('successAlert');
    
    if (errAlert) errAlert.classList.remove('show');
    if (successAlert) successAlert.classList.remove('show');

    if (btn) {
        btn.disabled = true;
        btn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> MEMBUAT KEY...';
    }

    const keyValue = generateKey();
    const now = new Date();
    const expiresAt = new Date(now.getTime() + KEY_DURATION_MS);

    const payload = {
        key_value: keyValue,
        created_by: "user",
        created_at: now.toISOString(),
        expires_at: expiresAt.toISOString(),
        is_active: true,
        note: "Auto-generated by user"
    };

    console.log('%c[CREATE] Payload:', 'color:#ffd700;', payload);

    let savedToDB = false;
    let savedId = null;
    let lastError = '';

    // ===== ENDPOINT UTAMA =====
    try {
        const res = await fetch(`${DB_BASE}/${COLLECTION}`, {
            method: 'POST',
            headers: {
                'x-api-key': DB_API_KEY,
                'Content-Type': 'application/json',
                'Accept': 'application/json'
            },
            body: JSON.stringify(payload)
        });

        const rawText = await res.text();
        let data;
        try { data = JSON.parse(rawText); } catch { data = rawText; }

        console.log(`%c[CREATE] Response Status: ${res.status}`, 
            res.status >= 200 && res.status < 300 ? 'color:#00ff88; font-weight:bold;' : 'color:#ff6666;');
        console.log('[CREATE] Response Body:', data);

        if (res.status >= 200 && res.status < 300) {
            savedToDB = true;
            if (data && typeof data === 'object' && data.id) {
                savedId = data.id;
            }
            console.log('%c[CREATE] ✅ KEY SAVED!', 'color:#00ff88; font-weight:bold; font-size:14px;');
        } else {
            lastError = `Status ${res.status}`;
        }
    } catch (fetchErr) {
        console.error('[CREATE] Fetch error:', fetchErr);
        lastError = fetchErr.message;
    }

    // ===== ENDPOINT ALTERNATIF =====
    if (!savedToDB) {
        console.log('%c[CREATE] Trying alternative endpoints...', 'color:#ffaa00;');
        
        const altEndpoints = [
            `/${COLLECTION}/create`,
            `/${COLLECTION}/insert`
        ];

        for (const altPath of altEndpoints) {
            try {
                const res = await fetch(`${DB_BASE}${altPath}`, {
                    method: 'POST',
                    headers: {
                        'x-api-key': DB_API_KEY,
                        'Content-Type': 'application/json',
                        'Accept': 'application/json'
                    },
                    body: JSON.stringify(payload)
                });

                const rawText = await res.text();
                let data;
                try { data = JSON.parse(rawText); } catch { data = rawText; }

                console.log(`[CREATE] Alt ${altPath} → ${res.status}`, data);

                if (res.status >= 200 && res.status < 300) {
                    savedToDB = true;
                    if (data && typeof data === 'object' && data.id) {
                        savedId = data.id;
                    }
                    console.log('%c[CREATE] ✅ SUCCESS via alt!', 'color:#00ff88;');
                    break;
                }
            } catch (err) {
                console.error(`[CREATE] Alt error ${altPath}:`, err);
            }
        }
    }

    // ===== HASIL =====
    if (savedToDB) {
        // ✅ SUKSES
        currentKey = keyValue;
        currentKeyId = savedId;
        keyStartTime = Date.now();
        addToHistory(keyValue);
        
        const keyValueEl = document.getElementById('keyValue');
        const keyDisplayEl = document.getElementById('keyDisplay');
        if (keyValueEl) keyValueEl.textContent = keyValue;
        if (keyDisplayEl) keyDisplayEl.style.display = 'block';
        
        if (successAlert) {
            successAlert.innerHTML = '✅ <strong>Key berhasil dibuat!</strong> Copy sekarang sebelum expired.';
            successAlert.classList.add('show');
        }
        
        startTimer();
        setTimeout(() => {
            if (keyDisplayEl) keyDisplayEl.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }, 100);
    } else {
        showError('❌ Gagal simpan ke database' + (lastError ? ` (${lastError})` : ''));
        console.error('%c[CREATE] ❌ FAILED', 'color:#ff4444; font-weight:bold;');
    }

    if (btn) {
        btn.disabled = false;
        btn.innerHTML = '<i class="fas fa-magic"></i> BUAT KEY SEKARANG';
    }
}

function showError(msg) {
    const errAlert = document.getElementById('errorAlert');
    if (!errAlert) return;
    errAlert.textContent = msg;
    errAlert.classList.add('show');
    setTimeout(() => errAlert.classList.remove('show'), 5000);
}

// ================================================================
// TIMER KEY
// ================================================================
function startTimer() {
    if (timerInterval) clearInterval(timerInterval);
    updateTimerDisplay();
    timerInterval = setInterval(() => {
        const elapsed = Date.now() - keyStartTime;
        const remaining = KEY_DURATION_MS - elapsed;
        if (remaining <= 0) {
            clearInterval(timerInterval);
            timerInterval = null;
            expireKey();
            return;
        }
        updateTimerDisplay();
    }, 1000);
}

function updateTimerDisplay() {
    const elapsed = Date.now() - keyStartTime;
    const remaining = Math.max(0, KEY_DURATION_MS - elapsed);
    const mins = Math.floor(remaining / 60000);
    const secs = Math.floor((remaining % 60000) / 1000);
    
    const timerValue = document.getElementById('timerValue');
    const timerFill = document.getElementById('timerFill');
    
    if (timerValue) {
        timerValue.textContent = String(mins).padStart(2,'0') + ':' + String(secs).padStart(2,'0');
        
        if (remaining <= 30000) {
            timerValue.classList.add('urgent');
        } else {
            timerValue.classList.remove('urgent');
        }
    }
    
    if (timerFill) {
        const fillPercent = (remaining / KEY_DURATION_MS) * 100;
        timerFill.style.width = fillPercent + '%';
    }
}

async function expireKey() {
    if (currentKeyId) {
        try {
            await fetch(`${DB_BASE}/${COLLECTION}/${currentKeyId}`, {
                method: 'PUT',
                headers: {
                    'x-api-key': DB_API_KEY,
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ is_active: false })
            });
        } catch (e) {
            console.warn('Gagal mark expired:', e);
        }
    }
    
    const timerValue = document.getElementById('timerValue');
    const timerFill = document.getElementById('timerFill');
    const copyBtn = document.getElementById('copyBtn');
    
    if (timerValue) {
        timerValue.textContent = 'EXPIRED';
        timerValue.classList.add('urgent');
    }
    if (timerFill) timerFill.style.width = '0%';
    if (copyBtn) copyBtn.disabled = true;
    
    showError('⏰ Key sudah expired. Buat key baru.');
}

// ================================================================
// COPY KEY
// ================================================================
async function copyKey() {
    if (!currentKey) return;
    const btn = document.getElementById('copyBtn');
    if (!btn) return;
    
    try {
        await navigator.clipboard.writeText(currentKey);
        btn.innerHTML = '<i class="fas fa-check"></i> TERSALIN!';
        setTimeout(() => btn.innerHTML = '<i class="fas fa-copy"></i> SALIN', 2000);
    } catch {
        const ta = document.createElement('textarea');
        ta.value = currentKey;
        document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        document.body.removeChild(ta);
        btn.innerHTML = '<i class="fas fa-check"></i> TERSALIN!';
        setTimeout(() => btn.innerHTML = '<i class="fas fa-copy"></i> SALIN', 2000);
    }
}

function resetKey() {
    if (timerInterval) clearInterval(timerInterval);
    const keyDisplay = document.getElementById('keyDisplay');
    const copyBtn = document.getElementById('copyBtn');
    const timerValue = document.getElementById('timerValue');
    
    if (keyDisplay) keyDisplay.style.display = 'none';
    if (copyBtn) copyBtn.disabled = false;
    if (timerValue) timerValue.classList.remove('urgent');
    
    currentKey = null;
    currentKeyId = null;
}

// ================================================================
// INIT
// ================================================================
window.addEventListener('DOMContentLoaded', () => {
    renderHistory();
    console.log('%c🔑 Create Key Page Loaded', 'color:#ffd700; font-weight:bold; font-size:14px;');
    console.log('%c♾️ TANPA LIMIT — Bebas bikin key sepuasnya', 'color:#00ff88;');
});
</script>

</body>
</html>
