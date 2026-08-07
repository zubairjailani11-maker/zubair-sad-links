# zubair-sad-links
<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Zubair | Sad Era</title>
    <style>
        /* فونت حرفه‌ای */
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #0a0a12;
            font-family: 'Orbitron', sans-serif;
            overflow: hidden;
            position: relative;
        }

        /* ===== پس‌زمینه با افکت موج و گرید ===== */
        .bg-wrapper {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(100, 30, 150, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 50%, rgba(30, 60, 180, 0.12) 0%, transparent 50%),
                radial-gradient(circle at 50% 80%, rgba(180, 30, 80, 0.08) 0%, transparent 50%);
            z-index: 0;
        }

        /* افکت گرید 3D */
        .grid-3d {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
            background-size: 60px 60px;
            animation: grid3D 20s linear infinite;
            z-index: 0;
            pointer-events: none;
        }

        @keyframes grid3D {
            0% { transform: perspective(800px) rotateX(0deg) translateY(0); }
            100% { transform: perspective(800px) rotateX(3deg) translateY(60px); }
        }

        /* حلقه‌های نورانی چرخان */
        .glow-rings {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }

        .ring {
            position: absolute;
            border-radius: 50%;
            border: 1px solid rgba(200, 100, 255, 0.06);
            animation: ringRotate linear infinite;
        }

        .ring-1 {
            width: 500px;
            height: 500px;
            top: -150px;
            right: -150px;
            animation-duration: 20s;
            border-color: rgba(200, 100, 255, 0.08);
        }

        .ring-2 {
            width: 350px;
            height: 350px;
            bottom: -100px;
            left: -100px;
            animation-duration: 15s;
            animation-direction: reverse;
            border-color: rgba(255, 100, 150, 0.06);
        }

        .ring-3 {
            width: 250px;
            height: 250px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation-duration: 25s;
            border-color: rgba(100, 200, 255, 0.04);
        }

        @keyframes ringRotate {
            0% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(180deg) scale(1.1); }
            100% { transform: rotate(360deg) scale(1); }
        }

        /* ===== کارت اصلی ===== */
        .main-card {
            background: rgba(10, 10, 18, 0.8);
            backdrop-filter: blur(60px);
            border: 1px solid rgba(200, 100, 255, 0.1);
            border-radius: 50px 50px 30px 30px;
            padding: 40px 35px 30px;
            width: 420px;
            max-width: 92%;
            text-align: center;
            box-shadow: 
                0 0 100px rgba(200, 100, 255, 0.04),
                inset 0 0 100px rgba(200, 100, 255, 0.02);
            z-index: 10;
            position: relative;
            animation: cardFloat 7s ease-in-out infinite;
        }

        @keyframes cardFloat {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-12px) rotate(0.3deg); }
        }

        /* خطوط نئونی بالا و پایین کارت */
        .main-card::before,
        .main-card::after {
            content: '';
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            height: 2px;
            background: linear-gradient(90deg, transparent, rgba(200, 100, 255, 0.3), transparent);
        }

        .main-card::before {
            top: -1px;
            width: 50%;
            animation: neonLine 3s ease-in-out infinite;
        }

        .main-card::after {
            bottom: -1px;
            width: 30%;
            animation: neonLine 3s ease-in-out infinite reverse;
        }

        @keyframes neonLine {
            0%, 100% { opacity: 0.2; width: 30%; }
            50% { opacity: 1; width: 70%; }
        }

        /* ===== کاور (همون عکس پس‌زمینه) ===== */
        .cover-art {
            width: 100%;
            height: 130px;
            border-radius: 30px;
            margin-bottom: 15px;
            background: 
                linear-gradient(135deg, rgba(150, 50, 200, 0.15), rgba(50, 100, 200, 0.08)),
                repeating-linear-gradient(45deg, transparent, transparent 10px, rgba(255,255,255,0.01) 10px, rgba(255,255,255,0.01) 11px);
            border: 1px solid rgba(200, 100, 255, 0.06);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            animation: coverPulse 5s ease-in-out infinite;
        }

        .cover-art span {
            font-size: 2.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, rgba(200, 180, 255, 0.2), rgba(255, 150, 200, 0.1));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: 15px;
            animation: coverText 4s ease-in-out infinite;
        }

        @keyframes coverPulse {
            0%, 100% { opacity: 0.6; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.02); }
        }

        @keyframes coverText {
            0%, 100% { letter-spacing: 15px; opacity: 0.3; }
            50% { letter-spacing: 25px; opacity: 0.6; }
        }

        /* ===== ایموجی غمگین با افکت گلیچ ===== */
        .sad-glitch {
            font-size: 85px;
            display: block;
            margin-bottom: 5px;
            animation: glitchEffect 2.5s infinite;
            filter: drop-shadow(0 0 50px rgba(200, 100, 255, 0.15));
        }

        @keyframes glitchEffect {
            0%, 90%, 100% { transform: translate(0) scale(1); }
            92% { transform: translate(-4px, 2px) skewX(-3deg) scale(1.02); }
            94% { transform: translate(4px, -2px) skewX(3deg) scale(0.98); }
            96% { transform: translate(-2px, 1px) scale(1.01); }
        }

        /* ===== تایتل ===== */
        h1 {
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, #c8a0ff, #ff80b0, #c8a0ff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradShift 5s ease-in-out infinite;
            letter-spacing: 10px;
            margin-bottom: 2px;
        }

        @keyframes gradShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .sub-sad {
            color: rgba(200, 180, 220, 0.3);
            font-size: 0.55rem;
            letter-spacing: 8px;
            font-weight: 400;
            border-bottom: 1px solid rgba(200, 100, 255, 0.04);
            padding-bottom: 18px;
            margin-bottom: 18px;
        }

        /* ===== لینک‌ها ===== */
        .links-grid {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .link-sad {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 14px 20px;
            background: rgba(200, 100, 255, 0.02);
            border-radius: 18px;
            border: 1px solid rgba(200, 100, 255, 0.04);
            color: #b8a8d0;
            text-decoration: none;
            font-size: 0.7rem;
            letter-spacing: 2px;
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            position: relative;
            overflow: hidden;
        }

        .link-sad::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(200, 100, 255, 0.04), transparent);
            transition: left 0.6s;
        }

        .link-sad:hover {
            transform: translateX(8px) scale(1.02);
            border-color: rgba(200, 100, 255, 0.15);
            background: rgba(200, 100, 255, 0.04);
            box-shadow: 0 0 50px rgba(200, 100, 255, 0.03);
            color: #f0e8ff;
        }

        .link-sad:hover::before {
            left: 100%;
        }

        .link-sad .icon-sad {
            font-size: 1.2rem;
            width: 28px;
            text-align: center;
            opacity: 0.5;
            transition: 0.3s;
        }

        .link-sad:hover .icon-sad {
            opacity: 1;
            transform: scale(1.2) rotate(-5deg);
        }

        .link-sad .label-sad {
            flex: 1;
            text-align: left;
            margin-left: 12px;
        }

        .link-sad .arrow-sad {
            opacity: 0.15;
            transition: 0.3s;
            font-size: 0.8rem;
        }

        .link-sad:hover .arrow-sad {
            opacity: 0.6;
            transform: translateX(5px);
        }

        /* ===== پلیر آهنگ با استایل جدید ===== */
        .music-section {
            margin-top: 18px;
            padding: 14px 16px;
            background: rgba(200, 100, 255, 0.02);
            border-radius: 20px;
            border: 1px solid rgba(200, 100, 255, 0.04);
        }

        .music-section audio {
            width: 100%;
            height: 28px;
            outline: none;
            background: transparent;
            border-radius: 12px;
        }

        .music-section audio::-webkit-media-controls-panel {
            background: rgba(200, 100, 255, 0.03);
            border-radius: 12px;
        }

        .music-label-sad {
            color: rgba(200, 180, 220, 0.15);
            font-size: 0.45rem;
            letter-spacing: 6px;
            display: block;
            margin-bottom: 6px;
        }

        /* ===== فوتر ===== */
        .footer-final {
            margin-top: 16px;
            color: rgba(200, 180, 220, 0.06);
            font-size: 0.45rem;
            letter-spacing: 6px;
            animation: footerFade 4s ease-in-out infinite;
        }

        @keyframes footerFade {
            0%, 100% { opacity: 0.06; }
            50% { opacity: 0.2; }
        }

        /* ===== ذرات سیار ===== */
        .star-particle {
            position: fixed;
            border-radius: 50%;
            background: rgba(200, 180, 255, 0.04);
            pointer-events: none;
            animation: starDrift linear infinite;
            z-index: 0;
        }

        @keyframes starDrift {
            0% { transform: translateY(100vh) scale(0) rotate(0deg); opacity: 0; }
            10% { opacity: 0.2; }
            90% { opacity: 0.2; }
            100% { transform: translateY(-10vh) scale(1) rotate(720deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <!-- ===== پس‌زمینه ===== -->
    <div class="bg-wrapper"></div>
    <div class="grid-3d"></div>

    <div class="glow-rings">
        <div class="ring ring-1"></div>
        <div class="ring ring-2"></div>
        <div class="ring ring-3"></div>
    </div>

    <!-- ===== کارت اصلی ===== -->
    <div class="main-card">

        <!-- کاور (همون عکس پس‌زمینه) -->
        <div class="cover-art">
            <span>✦ ZUBAIR ✦</span>
        </div>

        <span class="sad-glitch">😔</span>
        <h1>ZUBAIR</h1>
        <div class="sub-sad">✦ LOST IN THE VOID ✦</div>

        <!-- ===== لینک‌ها با آدرس‌های خودت ===== -->
        <div class="links-grid">
            <a href="https://www.instagram.com/_._zubair_jailani_._707?igsh=MXJtYmJ6azk3Mm5qeA%3D%3D&utm_source=qr" target="_blank" class="link-sad">
                <span class="icon-sad">📸</span>
                <span class="label-sad">INSTAGRAM</span>
                <span class="arrow-sad">→</span>
            </a>
            <a href="https://snapchat.com/t/eNzzSTGq" target="_blank" class="link-sad">
                <span class="icon-sad">👻</span>
                <span class="label-sad">SNAPCHAT</span>
                <span class="arrow-sad">→</span>
            </a>
            <a href="https://t.me/traikz" target="_blank" class="link-sad">
                <span class="icon-sad">✈️</span>
                <span class="label-sad">TELEGRAM</span>
                <span class="arrow-sad">→</span>
            </a>
            <a href="https://www.tiktok.com/@z__ubair7" target="_blank" class="link-sad">
                <span class="icon-sad">🎵</span>
                <span class="label-sad">TIKTOK</span>
                <span class="arrow-sad">→</span>
            </a>
        </div>

        <!-- ===== پلیر آهنگ غمگین (با لوپ) ===== -->
        <div class="music-section">
            <span class="music-label-sad">♫ SAD LOOP ♫</span>
            <audio controls autoplay loop>
                <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3" type="audio/mpeg">
                مرورگرت آهنگ رو ساپورت نمی‌کنه :(
            </audio>
        </div>

        <div class="footer-final">✦ EVERYTHING WILL BE OKAY ✦</div>
    </div>

    <!-- ===== ساخت ذرات ===== -->
    <script>
        (function createStars() {
            for (let i = 0; i < 50; i++) {
                const star = document.createElement('div');
                star.className = 'star-particle';
                star.style.left = Math.random() * 100 + 'vw';
                star.style.width = star.style.height = (1 + Math.random() * 4) + 'px';
                star.style.animationDuration = (15 + Math.random() * 30) + 's';
                star.style.animationDelay = (Math.random() * 20) + 's';
                star.style.opacity = 0.05 + Math.random() * 0.1;
                document.body.appendChild(star);
            }
        })();
    </script>

</body>
</html>
