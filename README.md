<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Pengisian Rapor BEM Fahutan</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
        body {
            background: linear-gradient(135deg, #1a5928, #3bb54a);
            min-height: 100vh;
            overflow-x: hidden;
        }
        .glass-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }
        .btn-primary {
            background: linear-gradient(135deg, #2e8b57, #3cb371);
            color: white;
            border-radius: 30px;
            padding: 12px 30px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }
        .btn-primary::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transform: translateX(-100%);
        }
        .btn-primary:hover::after {
            animation: shine 1.5s infinite;
        }
        .btn-login {
            background: linear-gradient(135deg, #ff9d00, #ff6a00);
            color: white;
            border-radius: 30px;
            padding: 10px 24px;
            font-weight: 600;
            transition: all 0.3s ease;
            border: none;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }
        .btn-login:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }
        .btn-login::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transform: translateX(-100%);
        }
        .btn-login:hover::after {
            animation: shine 1.5s infinite;
        }
        @keyframes shine {
            100% {
                transform: translateX(100%);
            }
        }
        .floating {
            animation: float 3s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-15px); }
            100% { transform: translateY(0px); }
        }
        .pulse {
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        .bg-circles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }
        .bg-circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            animation: move-up 15s linear infinite;
        }
        @keyframes move-up {
            0% { transform: translateY(100vh) scale(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 0.8; }
            100% { transform: translateY(-100vh) scale(1); opacity: 0; }
        }
        .progress-bar {
            height: 10px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 5px;
            overflow: hidden;
            position: relative;
        }
        .progress-fill {
            height: 100%;
            border-radius: 5px;
            background: linear-gradient(90deg, #2e8b57, #3cb371);
            position: relative;
            overflow: hidden;
        }
        .progress-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            animation: progress-shine 2s infinite;
        }
        @keyframes progress-shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        .quote-card {
            position: relative;
            overflow: hidden;
        }
        .quote-card::before {
            content: '"';
            position: absolute;
            top: -20px;
            left: 10px;
            font-size: 120px;
            color: rgba(255, 255, 255, 0.1);
            font-family: serif;
        }
        .logo-spin {
            animation: spin 20s linear infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .logo-container {
            position: relative;
            overflow: hidden;
            border-radius: 50%;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.2);
        }
        .logo-container::after {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, rgba(255,255,255,0) 0%, rgba(255,255,255,0.8) 50%, rgba(255,255,255,0) 100%);
            transform: rotate(45deg);
            animation: shine-logo 3s infinite;
        }
        @keyframes shine-logo {
            0% { transform: translateX(-100%) rotate(45deg); }
            100% { transform: translateX(100%) rotate(45deg); }
        }
    </style>
</head>
<body>
    <!-- Background Animated Circles -->
    <div class="bg-circles">
        <div class="bg-circle" style="width: 100px; height: 100px; left: 10%; animation-duration: 20s;"></div>
        <div class="bg-circle" style="width: 150px; height: 150px; left: 30%; animation-duration: 25s; animation-delay: 2s;"></div>
        <div class="bg-circle" style="width: 80px; height: 80px; left: 60%; animation-duration: 18s; animation-delay: 5s;"></div>
        <div class="bg-circle" style="width: 200px; height: 200px; left: 80%; animation-duration: 22s; animation-delay: 8s;"></div>
        <div class="bg-circle" style="width: 120px; height: 120px; left: 20%; animation-duration: 23s; animation-delay: 10s;"></div>
        <div class="bg-circle" style="width: 180px; height: 180px; left: 50%; animation-duration: 19s; animation-delay: 15s;"></div>
    </div>
    <!-- Header -->
    <header class="relative py-6 px-4 md:px-10">
        <div class="container mx-auto flex justify-between items-center">
            <div class="flex items-center">
                <div class="w-12 h-12 bg-white rounded-full flex items-center justify-center mr-3 overflow-hidden">
                    <img src="https://iili.io/3bltue4.md.png" alt="Logo BEM Fahutan" class="w-10 h-10 object-contain">
                </div>
                <h1 class="text-white text-xl md:text-2xl font-bold">Sistem Rapor BEM Fahutan</h1>
            </div>
            <div class="flex items-center">
                <nav class="hidden md:flex space-x-6 mr-6">
                    <a href="#tentang" class="text-white hover:text-green-200 transition">Tentang</a>
                    <a href="#indikator" class="text-white hover:text-green-200 transition">Indikator</a>
                    <a href="#cara" class="text-white hover:text-green-200 transition">Cara Pengisian</a>
                    <a href="#pengisian" class="text-white hover:text-green-200 transition">Isi Rapor</a>
                </nav>
                <a href="https://pengisian-rapor-bemfahutan.my.canva.site/login-rapor-bem-fahutan" target="_blank" class="btn-login">
                    <span class="flex items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 16l-4-4m0 0l4-4m-4 4h14m-5 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h7a3 3 0 013 3v1" />
                        </svg>
                        Login
                    </span>
                </a>
            </div>
            <button class="md:hidden text-white" id="menu-toggle">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
            </button>
        </div>
        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden absolute top-20 left-0 right-0 bg-green-800 bg-opacity-90 backdrop-blur-md p-4 rounded-lg mx-4 z-50">
            <div class="flex flex-col space-y-3">
                <a href="#tentang" class="text-white hover:text-green-200 transition py-2 px-4 rounded hover:bg-green-700">Tentang</a>
                <a href="#indikator" class="text-white hover:text-green-200 transition py-2 px-4 rounded hover:bg-green-700">Indikator</a>
                <a href="#cara" class="text-white hover:text-green-200 transition py-2 px-4 rounded hover:bg-green-700">Cara Pengisian</a>
                <a href="#pengisian" class="text-white hover:text-green-200 transition py-2 px-4 rounded hover:bg-green-700">Isi Rapor</a>
                <a href="https://pengisian-rapor-bemfahutan.my.canva.site/login-rapor-bem-fahutan" target="_blank" class="text-white hover:text-green-200 transition py-2 px-4 rounded bg-orange-500 hover:bg-orange-600 flex items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 16l-4-4m0 0l4-4m-4 4h14m-5 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h7a3 3 0 013 3v1" />
                    </svg>
                    Login
                </a>
            </div>
        </div>
    </header>
    <!-- Hero Section -->
    <section class="py-10 md:py-16 px-4">
        <div class="container mx-auto flex flex-col md:flex-row items-center">
            <div class="md:w-1/2 mb-10 md:mb-0">
                <div class="flex items-center justify-center md:justify-start mb-8">
                    <div class="logo-container w-32 h-32 mr-4">
                        <img src="https://iili.io/3bltue4.md.png" alt="Logo BEM Fahutan" class="w-full h-full object-contain">
                    </div>
                </div>
                <h1 class="text-4xl md:text-5xl font-bold text-white leading-tight mb-6">Sistem Penilaian Kinerja BEM Fahutan</h1>
                <p class="text-green-100 text-lg mb-8">Evaluasi diri untuk membangun kabinet yang lebih berkualitas dan berdampak.</p>
                <a href="#pengisian" class="btn-primary inline-block">Isi Rapor Sekarang</a>
            </div>
            <div class="md:w-1/2 flex justify-center">
                <div class="glass-card p-6 w-full max-w-md floating">
                    <div class="flex items-center mb-6">
                        <div class="w-10 h-10 rounded-full bg-green-600 flex items-center justify-center mr-4">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" />
                            </svg>
                        </div>
                        <h3 class="text-white text-xl font-semibold">Rapor Triwulan</h3>
                    </div>
                    <div class="quote-card p-4 bg-white bg-opacity-10 rounded-lg mb-6">
                        <p class="text-white italic">"Evaluasi bukan untuk mencari kesalahan, tetapi untuk menemukan jalan menuju perbaikan dan kemajuan bersama."</p>
                    </div>
                    <div class="space-y-4">
                        <div>
                            <div class="flex justify-between text-sm text-white mb-1">
                                <span>Kontribusi</span>
                                <span>40%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 40%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between text-sm text-white mb-1">
                                <span>Keaktifan</span>
                                <span>30%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 30%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between text-sm text-white mb-1">
                                <span>Sikap</span>
                                <span>30%</span>
                            </div>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 30%"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <!-- About Section -->
    <section id="tentang" class="py-16 px-4">
        <div class="container mx-auto">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-white mb-4">Sekilas Tentang Rapor</h2>
                <div class="w-24 h-1 bg-green-300 mx-auto"></div>
            </div>
            <div class="glass-card p-8 max-w-3xl mx-auto">
                <div class="flex items-center justify-center mb-6">
                    <img src="https://iili.io/3bltue4.md.png" alt="Logo BEM Fahutan" class="w-16 h-16 object-contain mr-4">
                    <h3 class="text-2xl font-bold text-white">BEM Fahutan</h3>
                </div>
                <p class="text-white leading-relaxed mb-6">
                    Rapor adalah program yang dijalankan oleh Biro Internal dan Eksternal untuk menilai kinerja setiap individu. 
                    Rapor ini berfungsi sebagai bahan evaluasi untuk mengidentifikasi kelebihan yang perlu dipertahankan serta 
                    kekurangan yang harus diperbaiki.
                </p>
                <p class="text-white leading-relaxed">
                    Dengan adanya rapor, diharapkan dapat menjadi indikator yang jelas dalam memperbaiki setiap aspek di BEM Fahutan, 
                    sehingga membentuk kabinet yang lebih berkualitas.
                </p>
            </div>
        </div>
    </section>
    <!-- Indicators Section -->
    <section id="indikator" class="py-16 px-4 bg-green-900 bg-opacity-30">
        <div class="container mx-auto">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-white mb-4">Indikator Penilaian</h2>
                <div class="w-24 h-1 bg-green-300 mx-auto"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="glass-card p-6 pulse">
                    <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-white text-center mb-4">Kontribusi (40%)</h3>
                    <ul class="text-green-100 space-y-2">
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Mengatasi Masalah
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Cepat dalam menanggapi tugas
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Kemandirian
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Membantu rekan
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Inisiatif, saran, dan kritik
                        </li>
                    </ul>
                </div>
                <div class="glass-card p-6 pulse" style="animation-delay: 0.3s;">
                    <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-white text-center mb-4">Keaktifan (30%)</h3>
                    <ul class="text-green-100 space-y-2">
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Kehadiran
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Menyelesaikan tugas sesuai deadline
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Responsif
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Membantu proker BEM
                        </li>
                    </ul>
                </div>
                <div class="glass-card p-6 pulse" style="animation-delay: 0.6s;">
                    <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-white text-center mb-4">Sikap (30%)</h3>
                    <ul class="text-green-100 space-y-2">
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Komunikatif
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Menyikapi pendapat bertolak belakang
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Etika
                        </li>
                        <li class="flex items-start">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                            Menghargai setiap rekan kerja
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
    <!-- How to Fill Section -->
    <section id="cara" class="py-16 px-4">
        <div class="container mx-auto">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-white mb-4">Cara Pengisian Rapor</h2>
                <div class="w-24 h-1 bg-green-300 mx-auto"></div>
            </div>
            <div class="max-w-4xl mx-auto">
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="glass-card p-6 text-center">
                        <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-4">1. Persiapan</h3>
                        <ul class="text-green-100 space-y-3 text-left">
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Siapkan token yang sudah dibagikan
                            </li>
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Siapkan perangkat (laptop/smartphone)
                            </li>
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Siapkan link rapor yang dapat diakses di halaman akhir
                            </li>
                        </ul>
                    </div>
                    <div class="glass-card p-6 text-center">
                        <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z" />
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-4">2. Pengisian</h3>
                        <ul class="text-green-100 space-y-3 text-left">
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Masukkan token pada halaman awal Google Form
                            </li>
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Isi identitas dan validasi jabatan
                            </li>
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Isi setiap butir pertanyaan dengan skala 1-10
                            </li>
                        </ul>
                    </div>
                    <div class="glass-card p-6 text-center">
                        <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                            </svg>
                        </div>
                        <h3 class="text-xl font-bold text-white mb-4">3. Submit</h3>
                        <ul class="text-green-100 space-y-3 text-left">
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Klik submit jika sudah mengisi setiap pertanyaan
                            </li>
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Tunggu proses pengolahan nilai selesai
                            </li>
                            <li class="flex items-start">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-green-300 mr-2 mt-0.5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                </svg>
                                Hasil akan dikirimkan melalui email
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <!-- Quote Section -->
    <section class="py-16 px-4 bg-green-900 bg-opacity-30">
        <div class="container mx-auto">
            <div class="glass-card p-10 max-w-3xl mx-auto text-center">
                <div class="flex justify-center mb-6">
                    <img src="https://iili.io/3bltue4.md.png" alt="Logo BEM Fahutan" class="w-16 h-16 object-contain">
                </div>
                <h3 class="text-2xl font-bold text-white mb-6">Penilaian untuk Evaluasi Diri</h3>
                <p class="text-green-100 text-lg italic mb-6">
                    "Penilaian bukan untuk mencari kesalahan, tetapi untuk menemukan potensi yang belum tergali. 
                    Evaluasi diri adalah cermin yang memantulkan kekuatan dan kelemahan kita, 
                    sehingga kita dapat tumbuh menjadi versi terbaik dari diri kita sendiri."
                </p>
                <p class="text-green-100 text-lg">
                    Dengan menilai diri secara jujur, kita membuka pintu untuk perbaikan berkelanjutan dan 
                    pertumbuhan yang bermakna dalam perjalanan kita sebagai pengurus BEM Fahutan.
                </p>
            </div>
        </div>
    </section>
    <!-- Fill Report Section -->
    <section id="pengisian" class="py-16 px-4">
        <div class="container mx-auto">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-bold text-white mb-4">Isi Rapor Sekarang</h2>
                <div class="w-24 h-1 bg-green-300 mx-auto mb-6"></div>
                <p class="text-green-100 max-w-2xl mx-auto mb-10">
                    Pilih link sesuai dengan posisi Anda di BEM Fahutan. Pastikan Anda telah menyiapkan token yang telah dibagikan sebelumnya.
                </p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-4xl mx-auto">
                <div class="glass-card p-6 text-center hover:transform hover:scale-105 transition duration-300">
                    <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-4">BPH</h3>
                    <p class="text-green-100 mb-6">Untuk Ketua, Wakil Ketua, Sekretaris, dan Bendahara</p>
                    <a href="https://ipb.link/rapotanineks-bph" target="_blank" class="btn-primary inline-block w-full">
                        Isi Rapor BPH
                    </a>
                </div>
                <div class="glass-card p-6 text-center hover:transform hover:scale-105 transition duration-300">
                    <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-4">Departemen</h3>
                    <p class="text-green-100 mb-6">Untuk Kepala Departemen dan Staff Departemen</p>
                    <a href="https://ipb.link/rapotanineks-departemen" target="_blank" class="btn-primary inline-block w-full">
                        Isi Rapor Departemen
                    </a>
                </div>
                <div class="glass-card p-6 text-center hover:transform hover:scale-105 transition duration-300">
                    <div class="w-16 h-16 rounded-full bg-green-600 flex items-center justify-center mb-6 mx-auto">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" />
                        </svg>
                    </div>
                    <h3 class="text-xl font-bold text-white mb-4">Biro</h3>
                    <p class="text-green-100 mb-6">Untuk Kepala Biro dan Staff Biro</p>
                    <a href="https://ipb.link/rapotanineks-biro" target="_blank" class="btn-primary inline-block w-full">
                        Isi Rapor Biro
                    </a>
                </div>
            </div>
        </div>
    </section>
    <!-- Footer -->
    <footer class="py-10 px-4 bg-green-900 bg-opacity-50">
        <div class="container mx-auto">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="mb-6 md:mb-0 flex items-center">
                    <img src="https://iili.io/3bltue4.md.png" alt="Logo BEM Fahutan" class="w-12 h-12 object-contain mr-3">
                    <div>
                        <h3 class="text-xl font-bold text-white mb-2">Sistem Rapor BEM Fahutan</h3>
                        <p class="text-green-200">© 2025 Biro Internal dan Eksternal</p>
                    </div>
                </div>
                <div class="flex items-center">
                    <a href="https://www.instagram.com/ineks.bemfahutan/" target="_blank" class="flex items-center text-white hover:text-green-200 transition">
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" class="bi bi-instagram mr-2" viewBox="0 0 16 16">
                            <path d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0h.003zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"/>
                        </svg>
                        @ineks.bemfahutan
                    </a>
                </div>
            </div>
        </div>
    </footer>
    <script>
        // Mobile menu toggle
        const menuToggle = document.getElementById('menu-toggle');
        const mobileMenu = document.getElementById('mobile-menu');     
        menuToggle.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);             
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });               
                    // Hide mobile menu after clicking
                    if (!mobileMenu.classList.contains('hidden')) {
                        mobileMenu.classList.add('hidden');
                    }
                }
            });
        });
        // Create animated background circles
        function createBackgroundCircles() {
            const bgCircles = document.querySelector('.bg-circles');
            const numberOfCircles = 10;            
            for (let i = 0; i < numberOfCircles; i++) {
                const size = Math.random() * 150 + 50;
                const circle = document.createElement('div');
                circle.classList.add('bg-circle');
                circle.style.width = `${size}px`;
                circle.style.height = `${size}px`;
                circle.style.left = `${Math.random() * 100}%`;
                circle.style.animationDuration = `${Math.random() * 10 + 15}s`;
                circle.style.animationDelay = `${Math.random() * 10}s`;
                bgCircles.appendChild(circle);
            }
        }        
        createBackgroundCircles();
        // Add logo animation effect
        const logoElements = document.querySelectorAll('img[alt="Logo BEM Fahutan"]');
        logoElements.forEach(logo => {
            logo.addEventListener('mouseover', () => {
                logo.classList.add('logo-spin');
            });         
            logo.addEventListener('mouseout', () => {
                logo.classList.remove('logo-spin');
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'99620b31262761aa',t:'MTc2MTczNDMxMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
