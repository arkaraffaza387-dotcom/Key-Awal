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
.alert-warn { background: rgba(255,180,50,0.12); border: 1px solid rgba(255,180,50,0.4); color: #ffcc88; }

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

.input-group { margin-bottom: 16px; }
.input-label {
    color: #ffd700;
    font-size: 0.85rem;
    font-weight: 700;
    letter-spacing: 1px;
    margin-bottom: 8px;
    text-transform: uppercase;
    display: block;
}
.input-field {
    width: 100%;
    padding: 16px 20px;
    background: #0d0202;
    border: 2px solid rgba(184, 134, 11, 0.5);
    border-radius: 16px;
    color: #ffed4a;
    font-family: 'Courier New', monospace;
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 1px;
    transition: all 0.3s ease;
    outline: none;
}
.input-field:focus {
    border-color: #ffd700;
    box-shadow: 0 0 20px rgba(255, 215, 0, 0.3);
}

/* KEY DISPLAY */
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

/* TIMER */
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

/* ACTIONS */
.actions {
    display: flex;
    gap: 10px;
    margin-top: 16px;
}
.actions .btn { flex: 1; margin-top: 0; }

.badge {
    display: inline-block;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 10px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
}
.badge-expired { background: rgba(255,50,50,0.15); color: #ff6666; border: 1px solid #ff4444; }
.badge-active { background: rgba(0,255,136,0.15); color: #00ff88; border: 1px solid #00ff88; }

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

.limit-badge {
    text-align: center;
    font-size: 0.72rem;
    color: #cc9999;
    margin-bottom: 12px;
    letter-spacing: 1px;
}
.limit-badge strong { color: #ffd700; }
.limit-badge.warn strong { color: #ff6666; }

/* COUNTDOWN RESET */
.reset-info {
    text-align: center;
    padding: 10px 14px;
    margin-bottom: 14px;
    background: rgba(0,0,0,0.3);
    border: 1px dashed rgba(184, 134, 11, 0.5);
    border-radius: 12px;
    font-size: 0.72rem;
    color: #cc9999;
    letter-spacing: 1px;
    line-height: 1.6;
}
.reset-info .reset-time {
    font-family: 'Orbitron', monospace;
    font-size: 1rem;
    color: #ffd700;
    font-weight: 700;
    letter-spacing: 2px;
    display: block;
    margin-top: 4px;
    text-shadow: 0 0 15px rgba(255, 215, 0, 0.5);
}
.reset-info .reset-time.urgent { color: #00ff88; text-shadow: 0 0 20px rgba(0,255,136,0.8); }

/* LIMIT EXHAUSTED OVERLAY */
.limit-exhausted {
    background: rgba(255, 68, 68, 0.1);
    border: 1px solid rgba(255, 68, 68, 0.4);
    border-radius: 16px;
    padding: 16px;
    text-align: center;
    margin-bottom: 14px;
    display: none;
}
.limit-exhausted.show { display: block; animation: fadeIn 0.4s ease; }
.limit-exhausted h3 {
    color: #ff6666;
    font-size: 0.9rem;
    letter-spacing: 2px;
    margin-bottom: 6px;
    text-transform: uppercase;
}
.limit-exhausted p {
    color: #cc9999;
    font-size: 0.8rem;
    line-height: 1.6;
}
</style>
</head>
<body>

<div class="card">
    <h1 class="title">🔑 CREATE KEY</h1>
    <p class="subtitle">Buat key akses kamu sendiri</p>

    <div class="alert alert-info" id="infoAlert">
        <strong>ℹ️ Info:</strong> Key berlaku <strong>3 menit</strong>. Limit <strong>10 key</strong> per sesi, reset jam <strong>10:00</strong> & <strong>20:00</strong>.
    </div>

    <!-- LIMIT BADGE -->
    <div class="limit-badge" id="limitBadge">
        Limit Sesi: <strong id="usedCount">0</strong> / <strong>10</strong> key
    </div>

    <!-- RESET COUNTDOWN -->
    <div class="reset-info" id="resetInfo">
        🔄 Reset limit berikutnya dalam:
        <span class="reset-time" id="resetCountdown">--:--:--</span>
    </div>

    <!-- LIMIT EXHAUSTED -->
    <div class="limit-exhausted" id="limitExhausted">
        <h3>⚠️ LIMIT HABIS</h3>
        <p>Kamu sudah membuat 10 key. Tunggu reset berikutnya jam <strong id="nextResetTime">10:00</strong>.</p>
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
const MAX_KEYS_PER_SESSION = 10;

// ================================================================
// KONFIGURASI RESET (jam 10:00 & 20:00)
// ================================================================
const RESET_HOURS = [10, 20]; // Reset jam 10 pagi & 8 malam

/**
 * Hitung waktu reset berikutnya
 * @returns {Date} Waktu reset berikutnya
 */
function getNextResetTime() {
    const now = new Date();
    const currentHour = now.getHours();
    const currentMin = now.getMinutes();
    
    // Cari reset berikutnya hari ini
    for (const hour of RESET_HOURS) {
        if (currentHour < hour || (currentHour === hour && currentMin === 0)) {
            const reset = new Date(now);
            reset.setHours(hour, 0, 0, 0);
            if (reset > now) return reset;
        }
    }
    
    // Kalau sudah lewat semua reset hari ini, ambil reset pertama besok
    const reset = new Date(now);
    reset.setDate(reset.getDate() + 1);
    reset.setHours(RESET_HOURS[0], 0, 0, 0);
    return reset;
}

/**
 * Dapatkan ID sesi unik berdasarkan jam reset terakhir
 * Format: "YYYY-MM-DD-HH" (jam reset terakhir)
 */
function getCurrentSessionId() {
    const now = new Date();
    const currentHour = now.getHours();
    
    // Cari jam reset terakhir (yang sudah lewat)
    let lastResetHour = -1;
    for (const hour of RESET_HOURS) {
        if (currentHour >= hour) lastResetHour = hour;
    }
    
    // Kalau belum lewat reset hari ini, pakai reset terakhir kemarin
    if (lastResetHour === -1) {
        const yesterday = new Date(now);
        yesterday.setDate(yesterday.getDate() - 1);
        return `${yesterday.toISOString().slice(0,10)}-${RESET_HOURS[RESET_HOURS.length - 1]}`;
    }
    
    return `${now.toISOString().slice(0,10)}-${lastResetHour}`;
}

/**
 * Ambil jumlah key yang sudah dibuat di sesi ini
 */
function getSessionUsage() {
    const sessionId = getCurrentSessionId();
    const stored = localStorage.getItem('azfer_session_usage');
    
    if (!stored) return 0;
    
    try {
        const data = JSON.parse(stored);
        // Kalau session ID beda, berarti sudah reset → return 0
        if (data.sessionId !== sessionId) return 0;
        return data.count || 0;
    } catch {
        return 0;
    }
}

/**
 * Increment usage counter untuk sesi ini
 */
function incrementSessionUsage() {
    const sessionId = getCurrentSessionId();
    const currentCount = getSessionUsage();
    
    localStorage.setItem('azfer_session_usage', JSON.stringify({
        sessionId: sessionId,
        count: currentCount + 1,
        lastUpdate: Date.now()
    }));
    
    updateLimitBadge();
}

/**
 * Reset manual (untuk testing)
 */
function resetSessionUsage() {
    localStorage.removeItem('azfer_session_usage');
    updateLimitBadge();
}

// ================================================================
// STATE
// ================================================================
let currentKey = null;
let currentKeyId = null;
let timerInterval = null;
let keyStartTime = 0;
let resetCountdownInterval = null;

// ================================================================
// API
// ================================================================
async function apiRequest(method, path, body=null) {
    const url = DB_BASE + path;
    const opts = {
        method,
        headers: {
            'x-api-key': DB_API_KEY,
            'Content-Type': 'application/json',
            'Accept': 'application/json'
        }
    };
    if (body) opts.body = JSON.stringify(body);
    const res = await fetch(url, opts);
    const text = await res.text();
    let data;
    try { data = JSON.parse(text); } catch { data = text; }
    console.log(`[API ${method}] ${path} → ${res.status}`, data);
    return { ok: res.ok, status: res.status, data };
}

function parseArray(data) {
    if (Array.isArray(data)) return data;
    if (data && Array.isArray(data.data)) return data.data;
    if (data && Array.isArray(data.items)) return data.items;
    return [];
}

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
// LIMIT BADGE UPDATE
// ================================================================
function updateLimitBadge() {
    const used = getSessionUsage();
    const badge = document.getElementById('limitBadge');
    const exhausted = document.getElementById('limitExhausted');
    const createBtn = document.getElementById('createBtn');
    
    document.getElementById('usedCount').textContent = used;
    
    if (used >= MAX_KEYS_PER_SESSION) {
        badge.classList.add('warn');
        badge.innerHTML = `Limit Sesi: <strong>${used}</strong> / <strong>${MAX_KEYS_PER_SESSION}</strong> key (HABIS)`;
        exhausted.classList.add('show');
        createBtn.disabled = true;
        
        // Update next reset time text
        const nextReset = getNextResetTime();
        const hh = String(nextReset.getHours()).padStart(2, '0');
        const mm = String(nextReset.getMinutes()).padStart(2, '0');
        document.getElementById('nextResetTime').textContent = `${hh}:${mm}`;
    } else {
        badge.classList.remove('warn');
        badge.innerHTML = `Limit Sesi: <strong>${used}</strong> / <strong>${MAX_KEYS_PER_SESSION}</strong> key`;
        exhausted.classList.remove('show');
        createBtn.disabled = false;
    }
}

// ================================================================
// RESET COUNTDOWN
// ================================================================
function updateResetCountdown() {
    const el = document.getElementById('resetCountdown');
    if (!el) return;
    
    const now = Date.now();
    const nextReset = getNextResetTime();
    const diff = nextReset.getTime() - now;
    
    if (diff <= 0) {
        // Waktunya reset!
        el.textContent = '00:00:00';
        el.classList.add('urgent');
        // Cek apakah limit benar-benar direset
        setTimeout(() => {
            updateLimitBadge();
            updateResetCountdown();
        }, 1000);
        return;
    }
    
    const hours = Math.floor(diff / 3600000);
    const minutes = Math.floor((diff % 3600000) / 60000);
    const seconds = Math.floor((diff % 60000) / 1000);
    
    el.textContent = `${String(hours).padStart(2,'0')}:${String(minutes).padStart(2,'0')}:${String(seconds).padStart(2,'0')}`;
    
    if (diff <= 60000) { // < 1 menit
        el.classList.add('urgent');
    } else {
        el.classList.remove('urgent');
    }
}

// ================================================================
// KEY HISTORY
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
// CREATE KEY
// ================================================================
async function createKey() {
    const btn = document.getElementById('createBtn');
    const errAlert = document.getElementById('errorAlert');
    const successAlert = document.getElementById('successAlert');
    
    errAlert.classList.remove('show');
    successAlert.classList.remove('show');

    // Cek limit sesi
    if (getSessionUsage() >= MAX_KEYS_PER_SESSION) {
        const nextReset = getNextResetTime();
        const hh = String(nextReset.getHours()).padStart(2, '0');
        const mm = String(nextReset.getMinutes()).padStart(2, '0');
        showError(`❌ Limit habis! Tunggu reset jam ${hh}:${mm}.`);
        return;
    }

    btn.disabled = true;
    btn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> MEMBUAT KEY...';

    try {
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

        const attempts = [
            { method: 'POST', path: `/${COLLECTION}` },
            { method: 'POST', path: `/${COLLECTION}/create` },
            { method: 'POST', path: `/${COLLECTION}/insert` }
        ];

        let success = false;
        let lastRes = null;
        for (const a of attempts) {
            const res = await apiRequest(a.method, a.path, payload);
            lastRes = res;
            if (res.ok) {
                success = true;
                currentKeyId = res.data && res.data.id ? res.data.id : null;
                break;
            }
            if (res.status !== 404 && res.status !== 405) break;
        }

        if (!success) {
            throw new Error(`Gagal simpan ke database (status ${lastRes.status})`);
        }

        // Success
        currentKey = keyValue;
        keyStartTime = Date.now();
        incrementSessionUsage();
        addToHistory(keyValue);
        
        document.getElementById('keyValue').textContent = keyValue;
        document.getElementById('keyDisplay').style.display = 'block';
        successAlert.textContent = '✅ Key berhasil dibuat! Copy sekarang sebelum expired.';
        successAlert.classList.add('show');
        
        startTimer();
        document.getElementById('keyDisplay').scrollIntoView({ behavior: 'smooth', block: 'center' });

    } catch (err) {
        console.error(err);
        showError('❌ ' + err.message);
    } finally {
        btn.disabled = false;
        btn.innerHTML = '<i class="fas fa-magic"></i> BUAT KEY SEKARANG';
        updateLimitBadge();
    }
}

function showError(msg) {
    const errAlert = document.getElementById('errorAlert');
    errAlert.textContent = msg;
    errAlert.classList.add('show');
    setTimeout(() => errAlert.classList.remove('show'), 5000);
}

// ================================================================
// TIMER KEY (3 menit)
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
    timerValue.textContent = String(mins).padStart(2,'0') + ':' + String(secs).padStart(2,'0');
    
    const fillPercent = (remaining / KEY_DURATION_MS) * 100;
    document.getElementById('timerFill').style.width = fillPercent + '%';
    
    if (remaining <= 30000) {
        timerValue.classList.add('urgent');
    } else {
        timerValue.classList.remove('urgent');
    }
}

async function expireKey() {
    if (currentKeyId) {
        try {
            await apiRequest('PUT', `/${COLLECTION}/${currentKeyId}`, { is_active: false });
        } catch (e) {
            console.warn('Gagal mark expired:', e);
        }
    }
    
    document.getElementById('timerValue').textContent = 'EXPIRED';
    document.getElementById('timerValue').classList.add('urgent');
    document.getElementById('timerFill').style.width = '0%';
    document.getElementById('copyBtn').disabled = true;
    
    showError('⏰ Key sudah expired. Buat key baru.');
}

// ================================================================
// COPY KEY
// ================================================================
async function copyKey() {
    if (!currentKey) return;
    const btn = document.getElementById('copyBtn');
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
    document.getElementById('keyDisplay').style.display = 'none';
    document.getElementById('copyBtn').disabled = false;
    document.getElementById('timerValue').classList.remove('urgent');
    currentKey = null;
    currentKeyId = null;
}

// ================================================================
// INIT
// ================================================================
window.addEventListener('DOMContentLoaded', () => {
    updateLimitBadge();
    renderHistory();
    updateResetCountdown();
    
    // Update countdown tiap detik
    if (resetCountdownInterval) clearInterval(resetCountdownInterval);
    resetCountdownInterval = setInterval(() => {
        updateResetCountdown();
        // Cek juga apakah sudah reset
        const usage = getSessionUsage();
        const btn = document.getElementById('createBtn');
        if (usage < MAX_KEYS_PER_SESSION && btn.disabled) {
            updateLimitBadge();
        }
    }, 1000);
    
    console.log('%c🔑 Create Key Page Loaded', 'color:#ffd700; font-weight:bold;');
    console.log('%c⏰ Reset limit: jam 10:00 & 20:00', 'color:#ffd700;');
    console.log('%c📊 Session ID:', 'color:#ffd700;', getCurrentSessionId());
    console.log('%c📊 Current usage:', 'color:#ffd700;', getSessionUsage(), '/', MAX_KEYS_PER_SESSION);
});
</script>

</body>
</html>
