<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>10 Day/Night Theme Toggles | Creative Dark/Light Mode Switches</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* ============================================
           GLOBAL STYLES & CSS VARIABLES FOR THEME
           ============================================ */
        
        /* LIGHT THEME (Day) - Default */
        :root {
            --bg-body: #f0f4f8;
            --bg-card: #ffffff;
            --text-primary: #1e293b;
            --text-secondary: #475569;
            --border-light: #e2e8f0;
            --shadow: rgba(0, 0, 0, 0.05);
            --shadow-md: rgba(0, 0, 0, 0.1);
            --accent: #3b82f6;
            --code-bg: #f1f5f9;
            --header-bg: #f8fafc;
        }
        
        /* DARK THEME (Night) */
        [data-theme="dark"] {
            --bg-body: #0f172a;
            --bg-card: #1e293b;
            --text-primary: #f1f5f9;
            --text-secondary: #cbd5e1;
            --border-light: #334155;
            --shadow: rgba(0, 0, 0, 0.3);
            --shadow-md: rgba(0, 0, 0, 0.5);
            --accent: #60a5fa;
            --code-bg: #0f172a;
            --header-bg: #111827;
        }
        
        /* Smooth transitions for all themed elements */
        * {
            transition: background-color 0.3s ease, 
                        color 0.25s ease,
                        border-color 0.2s ease,
                        box-shadow 0.2s ease,
                        transform 0.2s ease;
        }
        
        body {
            font-family: 'Inter', system-ui, sans-serif;
            background: var(--bg-body);
            color: var(--text-primary);
            margin: 0;
            padding: 2rem;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1300px;
            margin: 0 auto;
        }
        
        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 2.5rem;
            padding: 1rem;
        }
        
        .header h1 {
            font-size: 2.2rem;
            background: linear-gradient(135deg, var(--accent), #8b5cf6);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        
        .header p {
            color: var(--text-secondary);
            margin-top: 0.5rem;
        }
        
        /* Grid Layout for 10 toggles */
        .toggles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 1.8rem;
            margin-bottom: 2rem;
        }
        
        /* Card style for each toggle demo */
        .toggle-card {
            background: var(--bg-card);
            border-radius: 1.5rem;
            padding: 1.5rem;
            box-shadow: 0 8px 20px var(--shadow-md);
            border: 1px solid var(--border-light);
            transition: transform 0.2s;
        }
        
        .toggle-card:hover {
            transform: translateY(-4px);
        }
        
        .card-title {
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--border-light);
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--accent);
        }
        
        .card-title i {
            font-size: 1.1rem;
        }
        
        .toggle-demo {
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 1.2rem;
            background: var(--bg-body);
            border-radius: 1rem;
            margin-bottom: 0.8rem;
        }
        
        .code-comment {
            font-size: 0.7rem;
            color: var(--text-secondary);
            background: var(--code-bg);
            padding: 0.6rem;
            border-radius: 0.8rem;
            font-family: monospace;
            margin-top: 0.8rem;
            border-left: 3px solid var(--accent);
        }
        
        hr {
            border-color: var(--border-light);
            margin: 2rem 0;
        }
        
        footer {
            text-align: center;
            padding: 1.5rem;
            color: var(--text-secondary);
            font-size: 0.8rem;
        }
        
        /* ============================================
           TOGGLE 1: SIMPLE SLIDER (iOS Style)
           ============================================ */
        .toggle-1 {
            position: relative;
            width: 70px;
            height: 34px;
        }
        .toggle-1 input {
            opacity: 0;
            width: 0;
            height: 0;
        }
        .slider1 {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #cbd5e1;
            border-radius: 34px;
            transition: 0.3s;
        }
        .slider1:before {
            position: absolute;
            content: "";
            height: 26px;
            width: 26px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            border-radius: 50%;
            transition: 0.3s;
        }
        [data-theme="dark"] .slider1 {
            background-color: #3b82f6;
        }
        [data-theme="dark"] .slider1:before {
            transform: translateX(36px);
            background-color: #f1f5f9;
        }
        
        /* ============================================
           TOGGLE 2: SUN & MOON ICON TOGGLE
           ============================================ */
        .toggle-2 {
            background: var(--border-light);
            border-radius: 50px;
            width: 80px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 8px;
            cursor: pointer;
            position: relative;
            border: none;
        }
        .toggle-2-icons {
            display: flex;
            justify-content: space-between;
            width: 100%;
            z-index: 1;
            pointer-events: none;
        }
        .toggle-2-knob {
            position: absolute;
            width: 32px;
            height: 32px;
            background: white;
            border-radius: 50%;
            left: 4px;
            transition: transform 0.3s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        [data-theme="dark"] .toggle-2-knob {
            transform: translateX(40px);
            background: #fbbf24;
        }
        .sun-icon { color: #f59e0b; }
        .moon-icon { color: #475569; }
        [data-theme="dark"] .moon-icon { color: #a5b4fc; }
        
        /* ============================================
           TOGGLE 3: NEUMORPHIC TOGGLE
           ============================================ */
        .toggle-3 {
            width: 80px;
            height: 40px;
            background: var(--bg-body);
            border-radius: 40px;
            box-shadow: 6px 6px 12px rgba(0,0,0,0.1), -6px -6px 12px rgba(255,255,255,0.2);
            cursor: pointer;
            position: relative;
            border: none;
        }
        .toggle-3-knob {
            width: 32px;
            height: 32px;
            background: var(--accent);
            border-radius: 50%;
            position: absolute;
            top: 4px;
            left: 4px;
            transition: transform 0.3s;
            box-shadow: 2px 2px 6px rgba(0,0,0,0.2);
        }
        [data-theme="dark"] .toggle-3-knob {
            transform: translateX(40px);
            background: #60a5fa;
        }
        
        /* ============================================
           TOGGLE 4: BUTTON WITH DAY/NIGHT TEXT
           ============================================ */
        .toggle-4 {
            background: var(--accent);
            border: none;
            padding: 10px 24px;
            border-radius: 40px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.9rem;
        }
        .toggle-4:hover {
            transform: scale(0.96);
        }
        
        /* ============================================
           TOGGLE 5: ANIMATED SWITCH WITH EMOJI
           ============================================ */
        .toggle-5 {
            width: 90px;
            height: 44px;
            background: #e2e8f0;
            border-radius: 44px;
            display: flex;
            align-items: center;
            padding: 0 6px;
            cursor: pointer;
            position: relative;
            justify-content: space-between;
        }
        .toggle-5-emoji {
            font-size: 1.3rem;
            z-index: 1;
            pointer-events: none;
            padding: 0 4px;
        }
        .toggle-5-ball {
            position: absolute;
            width: 36px;
            height: 36px;
            background: white;
            border-radius: 50%;
            left: 4px;
            transition: transform 0.3s;
            box-shadow: 0 2px 8px rgba(0,0,0,0.15);
        }
        [data-theme="dark"] .toggle-5 {
            background: #334155;
        }
        [data-theme="dark"] .toggle-5-ball {
            transform: translateX(46px);
            background: #fbbf24;
        }
        
        /* ============================================
           TOGGLE 6: GLASS MORPHISM TOGGLE
           ============================================ */
        .toggle-6 {
            width: 75px;
            height: 36px;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(8px);
            border-radius: 36px;
            border: 1px solid rgba(255,255,255,0.3);
            cursor: pointer;
            position: relative;
        }
        .toggle-6-handle {
            width: 28px;
            height: 28px;
            background: white;
            border-radius: 50%;
            position: absolute;
            top: 4px;
            left: 4px;
            transition: transform 0.3s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        [data-theme="dark"] .toggle-6-handle {
            transform: translateX(39px);
            background: #a5b4fc;
        }
        [data-theme="dark"] .toggle-6 {
            background: rgba(0,0,0,0.4);
            border-color: rgba(255,255,255,0.2);
        }
        
        /* ============================================
           TOGGLE 7: PILL WITH TEXT INSIDE
           ============================================ */
        .toggle-7 {
            width: 100px;
            height: 42px;
            background: #cbd5e1;
            border-radius: 42px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 12px;
            cursor: pointer;
            position: relative;
            font-size: 0.8rem;
            font-weight: 600;
        }
        .toggle-7 span {
            z-index: 1;
            color: #475569;
        }
        .toggle-7-slider {
            position: absolute;
            width: 48px;
            height: 36px;
            background: white;
            border-radius: 36px;
            left: 3px;
            transition: transform 0.3s;
        }
        [data-theme="dark"] .toggle-7 {
            background: #334155;
        }
        [data-theme="dark"] .toggle-7-slider {
            transform: translateX(46px);
            background: #3b82f6;
        }
        [data-theme="dark"] .toggle-7 span:first-child { color: #94a3b8; }
        [data-theme="dark"] .toggle-7 span:last-child { color: white; }
        
        /* ============================================
           TOGGLE 8: ROTATING ICON TOGGLE
           ============================================ */
        .toggle-8 {
            width: 60px;
            height: 60px;
            background: var(--bg-card);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            border: 2px solid var(--border-light);
            box-shadow: 0 4px 12px var(--shadow);
            font-size: 1.8rem;
        }
        .toggle-8 i {
            transition: transform 0.4s, color 0.2s;
        }
        [data-theme="dark"] .toggle-8 i {
            transform: rotate(360deg);
            color: #fbbf24;
        }
        .toggle-8 i {
            color: #f59e0b;
        }
        
        /* ============================================
           TOGGLE 9: VERTICAL SLIDER TOGGLE
           ============================================ */
        .toggle-9 {
            width: 50px;
            height: 90px;
            background: #cbd5e1;
            border-radius: 50px;
            position: relative;
            cursor: pointer;
        }
        .toggle-9-knob {
            width: 40px;
            height: 40px;
            background: white;
            border-radius: 50%;
            position: absolute;
            bottom: 5px;
            left: 5px;
            transition: transform 0.3s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        [data-theme="dark"] .toggle-9 {
            background: #334155;
        }
        [data-theme="dark"] .toggle-9-knob {
            transform: translateY(-40px);
            background: #60a5fa;
        }
        
        /* ============================================
           TOGGLE 10: BORDER ANIMATED TOGGLE
           ============================================ */
        .toggle-10 {
            width: 70px;
            height: 34px;
            background: transparent;
            border: 2px solid var(--accent);
            border-radius: 34px;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        .toggle-10-fill {
            position: absolute;
            width: 50%;
            height: 100%;
            background: var(--accent);
            border-radius: 34px;
            left: 0;
            transition: transform 0.3s;
        }
        .toggle-10-icon {
            position: absolute;
            right: 8px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 0.8rem;
            color: var(--accent);
            z-index: 1;
        }
        .toggle-10-icon-left {
            position: absolute;
            left: 8px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 0.8rem;
            color: white;
            z-index: 1;
        }
        [data-theme="dark"] .toggle-10-fill {
            transform: translateX(100%);
        }
    </style>
</head>
<body>
<div class="container">
    <div class="header">
        <h1><i class="fas fa-adjust"></i> 10 Day/Night Theme Toggles</h1>
        <p>Each toggle switches between light (day) and dark (night) mode | Click any toggle to change global theme</p>
    </div>

    <div class="toggles-grid">
        <!-- TOGGLE 1: Simple Slider (iOS Style) -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-toggle-on"></i> 1. iOS Slider</div>
            <div class="toggle-demo">
                <label class="toggle-1" id="toggle1">
                    <input type="checkbox" id="cb1" style="display: none;">
                    <span class="slider1"></span>
                </label>
            </div>
            <div class="code-comment">// Classic iOS-style slider toggle<br>// Click toggles data-theme attribute</div>
        </div>

        <!-- TOGGLE 2: Sun & Moon Icon Toggle -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-sun"></i> 2. Sun/Moon Switch</div>
            <div class="toggle-demo">
                <button class="toggle-2" id="toggle2">
                    <div class="toggle-2-icons">
                        <i class="fas fa-sun sun-icon"></i>
                        <i class="fas fa-moon moon-icon"></i>
                    </div>
                    <div class="toggle-2-knob"></div>
                </button>
            </div>
            <div class="code-comment">// Animated knob with sun/moon icons<br>// Visual feedback for day/night</div>
        </div>

        <!-- TOGGLE 3: Neumorphic Toggle -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-cube"></i> 3. Neumorphic</div>
            <div class="toggle-demo">
                <button class="toggle-3" id="toggle3">
                    <div class="toggle-3-knob"></div>
                </button>
            </div>
            <div class="code-comment">// Soft UI / Neumorphism design<br>// Embossed effect with shadows</div>
        </div>

        <!-- TOGGLE 4: Button with Text -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-font"></i> 4. Text Button</div>
            <div class="toggle-demo">
                <button class="toggle-4" id="toggle4">
                    <i class="fas fa-moon" id="toggle4Icon"></i>
                    <span id="toggle4Text">Dark Mode</span>
                </button>
            </div>
            <div class="code-comment">// Simple button with dynamic text & icon<br>// Changes label based on current theme</div>
        </div>

        <!-- TOGGLE 5: Animated Switch with Emoji -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-smile"></i> 5. Emoji Switch</div>
            <div class="toggle-demo">
                <div class="toggle-5" id="toggle5">
                    <span class="toggle-5-emoji">☀️</span>
                    <span class="toggle-5-emoji">🌙</span>
                    <div class="toggle-5-ball"></div>
                </div>
            </div>
            <div class="code-comment">// Fun emoji-based toggle<br>// Sun and moon emojis slide</div>
        </div>

        <!-- TOGGLE 6: Glassmorphism Toggle -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-glass-cheers"></i> 6. Glassmorphic</div>
            <div class="toggle-demo">
                <div class="toggle-6" id="toggle6">
                    <div class="toggle-6-handle"></div>
                </div>
            </div>
            <div class="code-comment">// Frosted glass effect<br>// Blur background & semi-transparent</div>
        </div>

        <!-- TOGGLE 7: Pill with Text Inside -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-pills"></i> 7. Pill Text Toggle</div>
            <div class="toggle-demo">
                <div class="toggle-7" id="toggle7">
                    <span>DAY</span>
                    <span>NIGHT</span>
                    <div class="toggle-7-slider"></div>
                </div>
            </div>
            <div class="code-comment">// Pill-shaped toggle with DAY/NIGHT labels<br>// Sliding pill indicator</div>
        </div>

        <!-- TOGGLE 8: Rotating Icon Toggle -->
        <div class="toggle-card">
            <div class="card-title"><i class="fas fa-sync-alt"></i> 8. Rotating Icon</div>
            <div class="toggle-demo">
                <div class="toggle-8" id="toggle8">
                    <i class="fas fa-sun"></i>
                </div>
            </div>
            <div clas
