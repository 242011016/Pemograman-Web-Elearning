# Pemograman-Web-Elearning
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nama Mahasiswa</title>
    <style>
        body {
            margin: 0;
            padding: 48px 20px;
            background-color: #eaf3ff;
            color: #23344d;
            font-family: Arial, sans-serif;
        }

        main {
            max-width: 640px;
            margin: 0 auto;
            padding: 32px;
            background-color: #ffffff;
            border-radius: 12px;
            animation: masuk 700ms ease-out both;
        }

        h1 {
            animation: muncul 600ms 120ms ease-out both;
        }

        .foto-belajar {
            position: relative;
            overflow: hidden;
            aspect-ratio: 16 / 9;
            margin: 24px 0;
            border-radius: 10px;
            box-shadow: 0 16px 32px rgb(35 52 77 / 18%);
            animation: reveal-gambar 900ms 250ms ease-out both;
        }

        .foto-belajar img {
            display: block;
            width: 100%;
            height: 100%;
            object-fit: cover;
            animation: melayang 6s ease-in-out 1s infinite alternate;
        }

        .foto-belajar::after {
            position: absolute;
            inset: 0;
            background: linear-gradient(110deg, transparent 30%, rgb(255 255 255 / 28%) 48%, transparent 66%);
            content: "";
            transform: translateX(-120%);
            animation: sapuan-cahaya 5s 1.5s ease-in-out infinite;
            pointer-events: none;
        }

        main > p:nth-of-type(1) {
            animation: muncul 600ms 240ms ease-out both;
        }

        main > p:nth-of-type(2) {
            animation: muncul 600ms 360ms ease-out both;
        }

        main > p:nth-of-type(3) {
            animation: muncul 600ms 480ms ease-out both;
        }

        button {
            padding: 10px 16px;
            border: 0;
            border-radius: 6px;
            background-color: #2563a6;
            color: #ffffff;
            font: inherit;
            cursor: pointer;
            transition: transform 180ms ease, background-color 180ms ease;
            animation: muncul 600ms 600ms ease-out both;
        }

        button:hover {
            background-color: #174b82;
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(0);
        }

        #waktu {
            min-height: 1.5em;
        }

        @keyframes masuk {
            from {
                opacity: 0;
                transform: translateY(18px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes muncul {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes reveal-gambar {
            from {
                opacity: 0;
                clip-path: inset(0 0 100% 0 round 10px);
                transform: translateY(16px) scale(0.98);
            }
            to {
                opacity: 1;
                clip-path: inset(0 0 0 0 round 10px);
                transform: translateY(0) scale(1);
            }
        }

        @keyframes melayang {
            from {
                transform: scale(1.02) translateY(0);
            }
            to {
                transform: scale(1.08) translateY(-8px);
            }
        }

        @keyframes sapuan-cahaya {
            0%, 55% {
                transform: translateX(-120%);
            }
            100% {
                transform: translateX(120%);
            }
        }

        @media (prefers-reduced-motion: reduce) {
            *,
            *::before,
            *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                scroll-behavior: auto !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>
<body>
    <main>
        <h1>Muhammad Raihan Anugrah</h1>
        <figure class="foto profile">
            <img src="images/Ehan.foto.jpeg" width="335" height="450" alt="Foto Saya" />
        </figure>
        <p>Halo! Saya Muhammad Raihan Anugrah, seorang mahasiswa yang senang belajar dan mencoba hal-hal baru.</p>
        <p>Saat ini saya sedang mendalami teknologi web, termasuk HTML, CSS, dan JavaScript.</p>
        <p>Di waktu luang, saya suka membaca, mendengarkan musik, dan mengerjakan proyek kreatif.</p>
        <button id="tombol-waktu" type="button">Tampilkan waktu</button>
        <p id="waktu" aria-live="polite"></p>
    </main>

    <script>
        document.getElementById("tombol-waktu").addEventListener("click", function () {
            document.getElementById("waktu").textContent =
                "Waktu saat ini: " + new Date().toLocaleString("id-ID");
        });
    </script>
</body>
</html>
