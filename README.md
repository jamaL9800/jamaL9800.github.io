<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Portal</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', sans-serif; }
        body { background: radial-gradient(circle at center, #1a1a2e, #0f0f1a); color: #fff; min-height: 100vh; display: flex; justify-content: center; align-items: center; overflow-x: hidden; }
        
        /* Secure Password Gate */
        #login-screen { position: fixed; inset: 0; background: #0a0a14; display: flex; justify-content: center; align-items: center; z-index: 100; transition: 0.5s; }
        .login-card { background: rgba(255, 255, 255, 0.03); padding: 40px; border-radius: 16px; border: 1px solid rgba(255, 255, 255, 0.05); width: 100%; max-width: 350px; text-align: center; }
        .input-group { margin-bottom: 20px; text-align: left; }
        .input-group input { width: 100%; padding: 14px; background: #000; border: 1px solid rgba(255,255,255,0.1); border-radius: 8px; color: #fff; outline: none; text-align: center; font-size: 16px; letter-spacing: 2px; }
        .input-group input:focus { border-color: #7f00ff; }
        .login-btn { width: 100%; padding: 14px; background: #7f00ff; border: none; border-radius: 8px; color: #fff; font-weight: bold; cursor: pointer; transition: 0.3s; font-size: 14px; letter-spacing: 1px; }
        .login-btn:hover { background: #9d33ff; }
        
        /* Main Portal Dashboard */
        #portal-dashboard { width: 100%; max-width: 1200px; padding: 40px 20px; display: none; opacity: 0; transition: 0.5s; }
        header { text-align: center; margin-bottom: 40px; }
        header h1 { font-size: 32px; background: linear-gradient(45deg, #ff007f, #7f00ff); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        
        /* 3D App Grid */
        .grid-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 25px; margin-top: 30px; perspective: 1000px; }
        .portal-card { background: linear-gradient(135deg, rgba(255,255,255,0.05), rgba(255,255,255,0.01)); border: 1px solid rgba(255,255,255,0.1); padding: 30px 20px; border-radius: 16px; text-align: center; cursor: pointer; transition: transform 0.3s, box-shadow 0.3s; transform-style: preserve-3d; transform: rotateX(10deg); }
        .portal-card:hover { transform: rotateX(0deg) scale(1.05) translateY(-5px); border-color: rgba(255,255,255,0.3); }
        
        .card-whatsapp:hover { box-shadow: 0 10px 30px rgba(37, 211, 102, 0.3); }
        .card-tiktok:hover { box-shadow: 0 10px 30px rgba(254, 44, 85, 0.3); }
        .card-youtube:hover { box-shadow: 0 10px 30px rgba(255, 0, 0, 0.3); }
        .card-roblox:hover { box-shadow: 0 10px 30px rgba(255, 255, 255, 0.2); }
        .card-games:hover { box-shadow: 0 10px 30px rgba(127, 0, 255, 0.4); }
        
        .card-icon { font-size: 40px; margin-bottom: 15px; display: inline-block; transform: translateZ(30px); }
        .portal-card h3 { font-size: 18px; margin-bottom: 8px; font-weight: 500; }
        .portal-card p { font-size: 12px; color: #aaa; }
    </style>
</head>
<body>

    <!-- Security Gate (No Hints) -->
    <div id="login-screen">
        <div class="login-card">
            <div class="input-group">
                <input type="password" id="password" placeholder="••••••••">
            </div>
            <button class="login-btn" onclick="tryLogin()">ENTER</button>
        </div>
    </div>

    <!-- Main Content Grid -->
    <div id="portal-dashboard">
        <header>
            <h1>INDEXHUBBY CORE PORTAL</h1>
            <p>Secure Hub v1.0.5 - 40+ Verified Virtual Nodes Active</p>
        </header>

        <div class="grid-container">
            <div class="portal-card card-whatsapp" onclick="alert('Launching WhatsApp Web Node Proxy...')">
                <span class="card-icon">💬</span>
                <h3>WhatsApp</h3>
                <p>Simulated Chat Interface</p>
            </div>
            <div class="portal-card card-tiktok" onclick="alert('Connecting to TikTok Feed Emulation...')">
                <span class="card-icon">🎵</span>
                <h3>TikTok</h3>
                <p>Embedded Video Stream</p>
            </div>
            <div class="portal-card card-roblox" onclick="alert('Roblox Client Simulator Launching...')">
                <span class="card-icon">🎮</span>
                <h3>Roblox</h3>
                <p>Cloud Server Gateway</p>
            </div>
            <div class="portal-card card-youtube" onclick="alert('YouTube Media Hub Syncing...')">
                <span class="card-icon">📺</span>
                <h3>YouTube</h3>
                <p>Global Content Link</p>
            </div>
            <div class="portal-card card-games" onclick="alert('Opening Gaming Vault: 40+ Title Directory...')">
                <span class="card-icon">🕹️</span>
                <h3>Gaming Vault</h3>
                <p>Browse 42 Arcade Titles</p>
            </div>
        </div>
    </div>

    <script>
        function tryLogin() {
            const pass = document.getElementById('password').value;
            
            // Password verification
            if(pass === "indexhubby") {
                document.getElementById('login-screen').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('login-screen').style.display = 'none';
                    const dash = document.getElementById('portal-dashboard');
                    dash.style.display = 'block';
                    setTimeout(() => dash.style.opacity = '1', 50);
                }, 500);
            } else {
                alert("Access Denied.");
                document.getElementById('password').value = "";
            }
        }
        
        // Allow pressing Enter key to submit
        document.getElementById('password').addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                tryLogin();
            }
        });
    </script>
</body>
</html>
