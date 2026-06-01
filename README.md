[index.html](https://github.com/user-attachments/files/28472643/index.html)
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ФК ПУШКАРЬ | Premium Official</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Montserrat:ital,wght@0,300;0,700;0,900;1,900&display=swap" rel="stylesheet">
    <style>
        :root {
            --red: #e31e24;
            --gold: #d4af37;
            --black-bg: #030303;
            --surface-1: #0a0a0a;
            --surface-glass: rgba(20, 20, 20, 0.6);
            --text-main: #ffffff;
            --text-muted: #737373;
            --space-sm: clamp(1rem, 2vw, 1.5rem);
            --space-md: clamp(2rem, 4vw, 3rem);
            --space-lg: clamp(4rem, 8vw, 6rem);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--black-bg);
            color: var(--text-main);
            line-height: 1.6;
            -webkit-font-smoothing: antialiased;
        }

        h1, h2, h3, .brand { font-family: 'Montserrat', sans-serif; text-transform: uppercase; }

        /* HEADER & SMART BUTTONS */
        header {
            position: fixed; top: 0; width: 100%;
            padding: var(--space-sm) 5%;
            display: flex; justify-content: space-between; align-items: center;
            background: rgba(3, 3, 3, 0.8); backdrop-filter: blur(15px);
            z-index: 100; border-bottom: 1px solid rgba(255,255,255,0.03);
        }

        .brand { font-weight: 900; font-size: clamp(1.2rem, 2.5vw, 1.5rem); letter-spacing: 2px; }
        .brand span { color: var(--red); }

        .header-links { display: flex; gap: 10px; }

        .btn-social {
            display: flex; align-items: center; justify-content: center;
            padding: 10px 24px; border-radius: 4px; border: none; cursor: pointer;
            font-size: 0.75rem; font-weight: 700; letter-spacing: 1px;
            text-transform: uppercase; text-decoration: none;
            transition: all 0.3s ease; font-family: 'Inter', sans-serif;
        }
        
        .btn-tg { background: var(--text-main); color: var(--black-bg); }
        .btn-tg:hover { background: var(--red); color: var(--text-main); }
        
        .btn-vk { background: #0077FF; color: #ffffff; }
        .btn-vk:hover { background: #005ce6; }

        .btn-icon { display: none; font-weight: 900; }

        /* HERO */
        .hero {
            height: 100vh; min-height: 500px;
            display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center;
            background: radial-gradient(circle at center, rgba(0,0,0,0.3) 0%, var(--black-bg) 100%), 
                        url('https://images.unsplash.com/photo-1556056504-5c7696c4c28d?q=80&w=2000') center/cover no-repeat;
            position: relative;
        }
        .hero::after { content: ''; position: absolute; bottom: 0; width: 100%; height: 40%; background: linear-gradient(to top, var(--black-bg), transparent); }

        .hero h1 { font-size: clamp(3rem, 12vw, 9rem); font-weight: 900; font-style: italic; line-height: 0.85; z-index: 2; }
        .hero-subtitle { font-size: clamp(0.7rem, 1.5vw, 1rem); color: var(--red); letter-spacing: 8px; font-weight: 600; z-index: 2; margin-bottom: 15px;}

        .container { max-width: 1400px; margin: 0 auto; padding: var(--space-lg) 5%; }
        
        .section-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: var(--space-md); flex-wrap: wrap; gap: 20px;}
        .section-title { font-size: clamp(2rem, 5vw, 3.5rem); font-weight: 300; line-height: 1; margin-bottom: 0;}

        /* MATCH CENTER TABS */
        .match-tabs { display: flex; gap: 10px; }
        .match-tab-btn {
            background: transparent; color: var(--text-muted); border: 1px solid rgba(255,255,255,0.1);
            padding: 8px 20px; border-radius: 30px; font-size: 0.75rem; text-transform: uppercase; letter-spacing: 1px;
            cursor: pointer; transition: all 0.3s ease; font-weight: 700;
        }
        .match-tab-btn.active, .match-tab-btn:hover { background: var(--red); color: var(--text-main); border-color: var(--red); }

        /* MATCH CENTER */
        .match-center {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px;
            margin-bottom: var(--space-lg);
        }

        .match-card {
            background: var(--surface-glass); backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.05); border-radius: 12px;
            padding: var(--space-md); text-align: center; cursor: pointer;
            transition: transform 0.3s ease, border-color 0.3s ease; display: flex; flex-direction: column; justify-content: center;
        }
        .match-card:hover { transform: translateY(-5px); border-color: rgba(255,255,255,0.2); background: rgba(30,30,30,0.6); }
        .mc-label { font-size: 0.7rem; color: var(--text-muted); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 20px; font-weight: 600;}
        .mc-teams { display: flex; justify-content: space-between; align-items: center; font-family: 'Montserrat', sans-serif; font-weight: 700; font-size: clamp(1rem, 2vw, 1.5rem);}
        .mc-score { font-size: 2.5rem; font-weight: 900; letter-spacing: 2px; color: var(--text-main); }
        .mc-vs { font-size: 1.5rem; color: var(--text-muted); }
        .mc-meta { margin-top: 20px; font-size: 0.75rem; color: var(--text-muted); }

        /* RECRUITMENT & ACADEMY */
        .info-strip { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; margin-bottom: var(--space-lg); }
        .info-block { background: var(--surface-1); padding: var(--space-md); border-radius: 12px; border-left: 4px solid var(--red); }
        .info-block h3 { font-size: 1.5rem; margin-bottom: 15px; color: var(--text-main); }
        .info-block p { color: var(--text-muted); font-size: 0.95rem; margin-bottom: 20px; }
        .tag-search { display: inline-block; background: rgba(227, 30, 36, 0.1); color: var(--red); padding: 5px 12px; border-radius: 4px; font-size: 0.7rem; font-weight: 700; text-transform: uppercase; margin-bottom: 10px; }

        /* SQUAD FILTERS */
        .filters { display: flex; gap: 15px; margin-bottom: 30px; flex-wrap: wrap; }
        .filter-btn {
            background: transparent; color: var(--text-muted); border: 1px solid rgba(255,255,255,0.1);
            padding: 8px 16px; border-radius: 30px; font-size: 0.75rem; text-transform: uppercase; letter-spacing: 1px;
            cursor: pointer; transition: all 0.3s ease;
        }
        .filter-btn.active, .filter-btn:hover { background: var(--text-main); color: var(--black-bg); border-color: var(--text-main); }

        /* SQUAD GRID */
        .squad-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 20px; margin-bottom: var(--space-lg); }
        .player-card {
            background: var(--surface-1); height: 320px; padding: var(--space-sm);
            display: flex; flex-direction: column; justify-content: flex-end; position: relative;
            border: 1px solid transparent; transition: all 0.4s ease; cursor: pointer;
        }
        .player-card:hover { border-color: rgba(255,255,255,0.1); background: #111; }
        .p-number { position: absolute; top: 15px; right: 15px; font-family: 'Montserrat'; font-size: 4rem; font-weight: 900; color: rgba(255,255,255,0.03); line-height: 0.8; transition: color 0.3s; }
        .player-card:hover .p-number { color: rgba(227, 30, 36, 0.2); }
        .p-name { font-size: 1.5rem; font-weight: 700; margin-bottom: 5px; }
        .p-pos { font-size: 0.7rem; color: var(--text-muted); letter-spacing: 2px; text-transform: uppercase; }

        /* TAGS */
        .tag-wrap { position: absolute; top: 15px; left: 15px; display: flex; flex-direction: column; gap: 5px; z-index: 2;}
        .tag { font-size: 0.55rem; font-weight: 700; padding: 4px 8px; letter-spacing: 1px; text-transform: uppercase; border-radius: 2px; }
        .tag-gold { background: rgba(212, 175, 55, 0.1); color: var(--gold); border: 1px solid rgba(212, 175, 55, 0.2); }
        .tag-red { background: rgba(227, 30, 36, 0.1); color: var(--red); border: 1px solid rgba(227, 30, 36, 0.2); }

        /* MEDIA HIGHLIGHTS BANNER */
        .media-banner {
            background: linear-gradient(45deg, #1a0000, #4d0000);
            border: 1px solid rgba(227, 30, 36, 0.3);
            border-radius: 12px; padding: var(--space-lg) var(--space-md); text-align: center;
            position: relative; overflow: hidden;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
        }
        .media-banner h3 { font-size: 2.5rem; margin-bottom: 10px; color: #fff; }
        .media-banner p { font-size: 1rem; margin-bottom: 30px; color: var(--text-muted); text-transform: uppercase; letter-spacing: 1px; font-weight: 600;}

        /* MEDIA MODAL SPECIFIC */
        .media-layout { display: grid; grid-template-columns: 2fr 1fr; gap: 20px; align-items: start; }
        .main-video-container { width: 100%; background: #000; border-radius: 8px; overflow: hidden; box-shadow: 0 10px 30px rgba(0,0,0,0.8); }
        .main-video-container video { width: 100%; display: block; outline: none; }
        
        .video-playlist { display: flex; flex-direction: column; gap: 10px; max-height: 400px; overflow-y: auto; padding-right: 5px; }
        .video-playlist::-webkit-scrollbar { width: 5px; }
        .video-playlist::-webkit-scrollbar-thumb { background: var(--red); border-radius: 5px;}
        
        .playlist-item { 
            display: flex; justify-content: space-between; align-items: center; 
            padding: 15px; background: rgba(255,255,255,0.03); 
            border: 1px solid rgba(255,255,255,0.05); border-radius: 8px; 
            cursor: pointer; transition: all 0.3s; 
        }
        .playlist-item:hover { background: rgba(255,255,255,0.08); border-color: rgba(255,255,255,0.2); }
        .playlist-item.active { background: rgba(227, 30, 36, 0.1); border-color: var(--red); border-left: 4px solid var(--red); }
        .playlist-title { font-weight: 700; font-family: 'Montserrat'; font-size: 0.9rem; }
        .playlist-status { font-size: 0.7rem; color: var(--text-muted); font-weight: 700; letter-spacing: 1px; }
        .playlist-item.active .playlist-status { color: var(--red); }

        /* MODALS (GENERAL) */
        .modal-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.9); backdrop-filter: blur(10px); z-index: 1000;
            display: none; justify-content: center; align-items: center; opacity: 0; transition: opacity 0.3s;
        }
        .modal-overlay.active { display: flex; opacity: 1; }
        .modal-card { background: var(--surface-1); width: 90%; max-width: 600px; max-height: 90vh; overflow-y: auto; padding: var(--space-md); border: 1px solid rgba(255,255,255,0.1); position: relative; border-radius: 12px; }
        .modal-card.wide { max-width: 1000px; }
        .modal-card::-webkit-scrollbar { width: 5px; }
        .modal-card::-webkit-scrollbar-thumb { background: var(--red); border-radius: 5px;}
        .modal-close { position: absolute; top: 15px; right: 20px; background: none; border: none; color: #fff; font-size: 2rem; cursor: pointer; transition: color 0.3s; z-index: 10;}
        .modal-close:hover { color: var(--red); }

        /* PLAYER MODAL SPECIFIC */
        .m-name { font-size: 2.5rem; font-family: 'Montserrat'; font-weight: 900; line-height: 1; margin-bottom: 5px;}
        .m-pos { color: var(--red); font-size: 0.8rem; letter-spacing: 2px; text-transform: uppercase; margin-bottom: 20px; }
        .m-desc { font-size: 0.9rem; color: var(--text-muted); margin-bottom: 30px; }
        .modal-stats { display: flex; gap: 40px; border-top: 1px solid rgba(255,255,255,0.1); padding-top: 20px; flex-wrap: wrap;}
        .m-stat-val { font-size: 2rem; font-weight: 300; font-family: 'Montserrat'; display: block; color: var(--text-main);}
        .m-stat-lbl { font-size: 0.65rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: 1px;}

        /* MATCH MODAL SPECIFIC */
        .match-detail-header { text-align: center; margin-bottom: 30px; }
        .md-tournament { font-size: 0.75rem; color: var(--red); letter-spacing: 2px; text-transform: uppercase; margin-bottom: 10px; font-weight: 700; }
        .md-teams-score { display: flex; justify-content: space-between; align-items: center; font-family: 'Montserrat'; margin-bottom: 10px;}
        .md-team { font-size: clamp(1.2rem, 3vw, 2rem); font-weight: 900; flex: 1; }
        .md-score { font-size: clamp(2.5rem, 5vw, 4rem); font-weight: 900; color: var(--gold); padding: 0 10px; white-space: nowrap; }
        .md-date { font-size: 0.8rem; color: var(--text-muted); }
        .md-section { background: rgba(255,255,255,0.03); border-radius: 8px; padding: 20px; margin-bottom: 20px; border: 1px solid rgba(255,255,255,0.05); }
        .md-section-title { font-size: 0.8rem; text-transform: uppercase; letter-spacing: 1px; color: var(--text-muted); margin-bottom: 15px; border-bottom: 1px solid rgba(255,255,255,0.1); padding-bottom: 5px; }

        /* ALL MATCHES LIST MODAL */
        .all-matches-list { display: flex; flex-direction: column; gap: 10px; margin-top: 20px; }
        .list-match-card { display: flex; justify-content: space-between; align-items: center; padding: 15px; background: rgba(255,255,255,0.03); border: 1px solid rgba(255,255,255,0.05); border-radius: 8px; cursor: pointer; transition: all 0.3s; }
        .list-match-card:hover { background: rgba(255,255,255,0.08); border-color: rgba(255,255,255,0.2); }
        .lmc-date { font-size: 0.7rem; color: var(--text-muted); width: 90px; }
        .lmc-teams { flex: 1; font-weight: 700; text-align: center; font-size: 1rem; font-family: 'Montserrat'; }
        .lmc-score { font-size: 1.2rem; font-weight: 900; color: var(--gold); width: 80px; text-align: right; }

        footer { text-align: center; padding: var(--space-lg) 5%; color: var(--text-muted); font-size: 0.75rem; border-top: 1px solid rgba(255,255,255,0.05); }

        /* MOBILE ADAPTATION */
        @media (max-width: 768px) {
            .btn-text { display: none; }
            .btn-icon { display: block; font-size: 1rem; }
            .btn-social { padding: 10px 15px; border-radius: 50%; }
            .section-header { flex-direction: column; align-items: flex-start; }
            .md-teams-score { flex-direction: column; }
            .md-score { padding: 10px 0; font-size: 3rem; }
            .list-match-card { flex-direction: column; gap: 10px; text-align: center; }
            .lmc-date, .lmc-score { width: auto; text-align: center; }
            .modal-stats { gap: 20px; }
            .media-layout { grid-template-columns: 1fr; }
            .video-playlist { max-height: 250px; }
        }
    </style>
</head>
<body>

<header>
    <div class="brand">ФК <span>ПУШКАРЬ</span></div>
    <div class="header-links">
        <a href="https://vk.com/club232317197" class="btn-social btn-vk" target="_blank">
            <span class="btn-text">Мы ВКонтакте</span>
            <span class="btn-icon">VK</span>
        </a>
        <a href="https://t.me/PushkarGorodna" class="btn-social btn-tg" target="_blank">
            <span class="btn-text">Перейти в Telegram</span>
            <span class="btn-icon">TG</span>
        </a>
    </div>
</header>

<section class="hero">
    <div class="hero-subtitle">СИЛА. ЧЕСТЬ. ГОРОДНА.</div>
    <h1>ПУШКАРЬ</h1>
</section>

<div class="container">
    
    <div class="section-header">
        <h2 class="section-title">МАТЧ-ЦЕНТР</h2>
        <div style="display: flex; gap: 15px; align-items: center; flex-wrap: wrap;">
            <div class="match-tabs">
                <button class="match-tab-btn active" onclick="setMatchFilter('regular')">Обычные</button>
                <button class="match-tab-btn" onclick="setMatchFilter('tournament')">Турниры</button>
            </div>
            <button class="btn-social btn-tg" style="background: var(--surface-1); border: 1px solid var(--red); color: var(--red);" onclick="openAllMatchesModal()">Все матчи</button>
        </div>
    </div>
    
    <div class="match-center" id="match-center-root"></div>

    <div class="info-strip">
        <div class="info-block">
            <div class="tag-search">Active Search</div>
            <h3>МЫ ИЩЕМ ТАЛАНТЫ</h3>
            <p>ФК ПУШКАРЬ объявляет активный поиск новых игроков. Если ты готов биться за цвета Городны, обладаешь техникой и командным духом — мы ждем тебя на просмотре.</p>
            <a href="https://vk.com/club232317197" class="btn-social btn-vk" style="display: inline-flex; font-size: 0.6rem; padding: 8px 15px;" target="_blank">Связаться</a>
        </div>
        <div class="info-block" style="border-left-color: var(--gold);">
            <div class="tag-search" style="background: rgba(212, 175, 55, 0.1); color: var(--gold);">Academy</div>
            <h3>ЛУХОВИЦЫ</h3>
            <p>Официальная футбольная академия «ПУШКАРЬ» в Луховицах. Мы растим новое поколение чемпионов с ранних лет.</p>
        </div>
    </div>

    <h2 class="section-title">КОМАНДА</h2>
    
    <div class="filters">
        <button class="filter-btn active" onclick="filterSquad('all')">Все</button>
        <button class="filter-btn" onclick="filterSquad('gk')">Вратари</button>
        <button class="filter-btn" onclick="filterSquad('def')">Защита</button>
        <button class="filter-btn" onclick="filterSquad('mid')">Полузащита</button>
        <button class="filter-btn" onclick="filterSquad('att')">Нападение</button>
    </div>

    <div class="squad-grid" id="squad-root"></div>

    <div class="media-banner">
        <h3>PUSHKAR HIGHLIGHTS</h3>
        <p>Архив лучших матчей и моментов команды</p>
        <button class="btn-social btn-tg" style="font-size: 1rem; padding: 15px 35px; border-radius: 8px;" onclick="openMediaModal()">
            ОТКРЫТЬ ВИДЕОГАЛЕРЕЮ
        </button>
    </div>

</div>

<!-- Модальное окно для Игроков -->
<div class="modal-overlay" id="playerModal">
    <div class="modal-card">
        <button class="modal-close" onclick="closeModals()">×</button>
        <div class="m-name" id="pName">NAME</div>
        <div class="m-pos" id="pPos">POSITION</div>
        <div class="m-desc" id="pDesc">Description</div>
        <div class="modal-stats">
            <div>
                <span class="m-stat-val" id="pNumber">00</span>
                <span class="m-stat-lbl">Номер</span>
            </div>
            <div>
                <span class="m-stat-val" id="pGoals">0</span>
                <span class="m-stat-lbl">Голы</span>
            </div>
            <div>
                <span class="m-stat-val" id="pAssists">0</span>
                <span class="m-stat-lbl">Ассисты</span>
            </div>
        </div>
    </div>
</div>

<!-- Модальное окно деталей матча -->
<div class="modal-overlay" id="matchDetailModal">
    <div class="modal-card">
        <button class="modal-close" onclick="closeModals()">×</button>
        <div class="match-detail-header">
            <div class="md-tournament" id="mdTournament">Матч</div>
            <div class="md-teams-score">
                <div class="md-team">ПУШКАРЬ</div>
                <div class="md-score" id="mdScore">0:0</div>
                <div class="md-team" id="mdOpponent">СОПЕРНИК</div>
            </div>
            <div class="md-date" id="mdDate">Дата матча</div>
        </div>
        
        <div class="md-section">
            <div class="md-section-title">Голы и события (Пушкарь)</div>
            <div id="mdGoalscorers" style="font-size: 0.9rem;">Нет данных</div>
        </div>
    </div>
</div>

<!-- Модальное окно: Все матчи -->
<div class="modal-overlay" id="allMatchesModal">
    <div class="modal-card">
        <button class="modal-close" onclick="closeModals()">×</button>
        <h3 style="font-size: 2rem; margin-bottom: 5px;">ВСЕ МАТЧИ</h3>
        <p style="color: var(--text-muted); font-size: 0.8rem; margin-bottom: 20px;">Полная история игр ФК Пушкарь (нажмите на матч для деталей)</p>
        <div class="all-matches-list" id="allMatchesListRoot"></div>
    </div>
</div>

<!-- НОВОЕ МОДАЛЬНОЕ ОКНО: Видеогалерея -->
<div class="modal-overlay" id="mediaModal">
    <div class="modal-card wide">
        <button class="modal-close" onclick="closeModals()">×</button>
        <h3 style="font-size: 1.5rem; margin-bottom: 20px; font-family: 'Montserrat';">ХАЙЛАЙТЫ ПУШКАРЯ</h3>
        
        <div class="media-layout">
            <div class="main-video-container">
                <!-- Убран тег source, путь теперь прописывается напрямую в video через JS -->
                <video id="mainVideoPlayer" controls playsinline preload="metadata">
                    Ваш браузер не поддерживает встроенные видео.
                </video>
            </div>
            
            <div class="video-playlist" id="videoPlaylistRoot">
                <!-- Сюда с помощью JS будет генерироваться список видео -->
            </div>
        </div>
    </div>
</div>

<footer>
    © 2026 ФК ПУШКАРЬ ГОРОДНА. ALL RIGHTS RESERVED.
</footer>

<script>
    // --- ПОЛНАЯ БАЗА МАТЧЕЙ ---
    const matchesData = [
        { id: 't4', type: 'tournament', tournament: 'Турнир ЛРЛ (Один день)', opponent: '4Медиа', scorePushkar: '0', scoreOpp: '3', date: '6 ИЮЛ 2025', goalscorers: '-', highlight: false },
        { id: 't5', type: 'tournament', tournament: 'Турнир ЛРЛ (Один день)', opponent: 'МФК Рвачи', scorePushkar: '0 (1)', scoreOpp: '0 (0)', date: '6 ИЮЛ 2025', goalscorers: 'Серия пенальти: Победный забил Матвей', highlight: true },
        { id: 't6', type: 'tournament', tournament: 'Турнир ЛРЛ (Один день)', opponent: 'Феникс', scorePushkar: '0', scoreOpp: '2', date: '6 ИЮЛ 2025', goalscorers: '-', highlight: false },
        { id: 't7', type: 'tournament', tournament: 'Турнир ЛРЛ (Один день)', opponent: 'ФК МЛД', scorePushkar: '1 (0)', scoreOpp: '1 (2)', date: '6 ИЮЛ 2025', goalscorers: 'Автогол (после удара Артёма)', highlight: false },
        { id: 'm4', type: 'regular', tournament: 'Регулярный матч', opponent: 'Sigma Boys', scorePushkar: '8', scoreOpp: '14', date: '20 АПР 2025', goalscorers: 'Артём (2), Лёха (2), Женя (2), Ваня (1), Автогол (1)', highlight: false },
        { id: 'm5', type: 'regular', tournament: 'Регулярный матч', opponent: 'ФК Скуфы', scorePushkar: '8', scoreOpp: '2', date: '9 МАЯ 2025', goalscorers: 'Артём (3), Матвей (3), Ваня (2)', highlight: false },
        { id: 'm6', type: 'regular', tournament: 'Регулярный матч', opponent: 'ФК Метеор', scorePushkar: '18', scoreOpp: '3', date: '23 ИЮЛ 2025', goalscorers: 'Матвей (8), Артём (8), Ваня (2)', highlight: true },
        { id: 'm7', type: 'regular', tournament: 'Регулярный матч', opponent: 'ФК Луховицы', scorePushkar: '5', scoreOpp: '1', date: '24 АВГ 2025', goalscorers: 'Матвей (5)', highlight: false },
        { id: 'm1', type: 'regular', tournament: 'Регулярный матч', opponent: 'ТОРНАДО', scorePushkar: '14', scoreOpp: '8', date: 'АПРЕЛЬ 2026', goalscorers: 'Командная победа', highlight: true },
        { id: 'm2', type: 'regular', tournament: 'Регулярный матч', opponent: 'ТОРНАДО', scorePushkar: '9', scoreOpp: '6', date: 'АПРЕЛЬ 2026', goalscorers: 'Артём (3), Ваня (2), Матвей (2), Лёха (2)', highlight: false },
    ];

    matchesData.reverse(); 

    // --- ОБНОВЛЕННАЯ БАЗА ИГРОКОВ ---
    const squadData = [
        { id: 18, name: "Матвей", pos: "Полузащитник", type: "mid", goals: 23, assists: 13, desc: "Капитан команды и безоговорочный лидер.", isCaptain: true, isFounder: false },
        { id: 10, name: "Артём", pos: "Нападающий", type: "att", goals: 19, assists: 11, desc: "Основатель. Двигатель команды в опорной зоне и атаке.", isCaptain: false, isFounder: true },
        { id: 11, name: "Ваня", pos: "Полузащитник", type: "mid", goals: 7, assists: 11, desc: "Креативный игрок атакующего плана.", isCaptain: false, isFounder: false },
        { id: 7, name: "Лёха", pos: "Нападающий", type: "att", goals: 5, assists: 0, desc: "Основатель. Классический форвард-завершитель.", isCaptain: false, isFounder: true },
        { id: 9, name: "Женя", pos: "Защитник", type: "def", goals: 2, assists: 2, desc: "Универсал с отличным подключением к стандартам.", isCaptain: false, isFounder: false },
        { id: 17, name: "Никита", pos: "Полузащитник", type: "mid", goals: 1, assists: 0, desc: "Полезный игрок ротации центра поля.", isCaptain: false, isFounder: false },
        { id: 1, name: "Ярик", pos: "Вратарь", type: "gk", goals: 0, assists: 1, desc: "Стена ворот.", isCaptain: false, isFounder: false },
        { id: 5, name: "Платон", pos: "Защитник", type: "def", goals: 0, assists: 1, desc: "Неуступчивый защитник, специалист по опеке.", isCaptain: false, isFounder: false },
        { id: 88, name: "Шаббат", pos: "Полузащитник", type: "mid", goals: 0, assists: 2, desc: "Свежая кровь в центре поля.", isCaptain: false, isFounder: false },
        { id: 8, name: "Оскар", pos: "Нападающий", type: "att", goals: 0, assists: 0, desc: "Важный игрок атакующей линии.", isCaptain: false, isFounder: false },
        { id: 14, name: "Кирилл", pos: "Защитник", type: "def", goals: 0, assists: 0, desc: "Обеспечивает тотальный контроль в центре обороны.", isCaptain: false, isFounder: false },
        { id: 6, name: "Вова", pos: "Защитник", type: "def", goals: 0, assists: 0, desc: "Надежный игрок оборонительной линии.", isCaptain: false, isFounder: false },
        { id: 24, name: "Игорь", pos: "Защитник", type: "def", goals: 0, assists: 0, desc: "Работоспособный игрок, выполняющий черновую работу.", isCaptain: false, isFounder: false },
        { id: 77, name: "Влад", pos: "Защитник", type: "def", goals: 0, assists: 0, desc: "Важное звено тактического построения защиты.", isCaptain: false, isFounder: false }
    ];

    // --- БАЗА ВИДЕОРОЛИКОВ ---
    const mediaData = [
        { id: 'v1', title: 'Пушкарь - Торнадо (14:8)', src: 'tornado_14_8.mp4' },
        { id: 'v2', title: 'Пример видео 2', src: 'example_video_2.mp4' },
        { id: 'v3', title: 'Пример видео 3', src: 'example_video_3.mp4' }
    ];

    // --- ЛОГИКА МАТЧ-ЦЕНТРА ---
    let currentMatchFilter = 'regular';
    const matchCenterRoot = document.getElementById('match-center-root');

    function setMatchFilter(type) {
        currentMatchFilter = type;
        document.querySelectorAll('.match-tab-btn').forEach(btn => btn.classList.remove('active'));
        event.target.classList.add('active');
        renderMatchCenter();
    }

    function renderMatchCenter() {
        matchCenterRoot.innerHTML = '';

        const filteredMatches = matchesData.filter(m => m.type === currentMatchFilter).slice(0, 3); 
        
        filteredMatches.forEach(m => {
            const isGold = m.highlight;
            const goldStyles = isGold ? `border-color: rgba(212, 175, 55, 0.3); background: linear-gradient(180deg, rgba(212, 175, 55, 0.05) 0%, transparent 100%); box-shadow: 0 0 30px rgba(212,175,55,0.05);` : '';
            const labelColor = isGold ? 'color: var(--gold);' : '';
            const scoreColor = isGold ? 'color: var(--gold);' : '';
            const labelText = m.type === 'tournament' ? m.tournament : (isGold ? 'Лучший матч' : 'Прошедший матч');

            const card = document.createElement('div');
            card.className = 'match-card';
            card.style.cssText = goldStyles;
            card.onclick = () => openMatchDetail(m);
            card.innerHTML = `
                <div class="mc-label" style="${labelColor}">${labelText}</div>
                <div class="mc-teams">
                    <div>ПУШКАРЬ</div>
                    <div class="mc-score" style="${scoreColor}">${m.scorePushkar}:${m.scoreOpp}</div>
                    <div style="color: var(--text-muted);">${m.opponent}</div>
                </div>
                <div class="mc-meta">${m.date}</div>
            `;
            matchCenterRoot.appendChild(card);
        });
    }

    // --- ЛОГИКА СОСТАВА ---
    const squadRoot = document.getElementById('squad-root');

    function renderSquad(filterType) {
        squadRoot.innerHTML = '';
        squadData.forEach(p => {
            if (filterType === 'all' || p.type === filterType) {
                let tags = '';
                if (p.isFounder) tags += `<div class="tag tag-gold">Основатель</div>`;
                if (p.isCaptain) tags += `<div class="tag tag-red">Капитан</div>`;

                const card = document.createElement('div');
                card.className = 'player-card';
                card.innerHTML = `
                    <div class="tag-wrap">${tags}</div>
                    <div class="p-number">${p.id}</div>
                    <div>
                        <div class="p-name">${p.name}</div>
                        <div class="p-pos">${p.pos}</div>
                    </div>
                `;
                card.onclick = () => openPlayerModal(p);
                squadRoot.appendChild(card);
            }
        });
    }

    function filterSquad(type) {
        document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
        event.target.classList.add('active');
        renderSquad(type);
    }

    // --- МОДАЛЬНЫЕ ОКНА ---
    const playerModal = document.getElementById('playerModal');
    const matchDetailModal = document.getElementById('matchDetailModal');
    const allMatchesModal = document.getElementById('allMatchesModal');
    const mediaModal = document.getElementById('mediaModal'); 
    const modals = [playerModal, matchDetailModal, allMatchesModal, mediaModal];

    function openPlayerModal(data) {
        document.getElementById('pName').innerText = data.name;
        document.getElementById('pPos').innerText = data.pos;
        document.getElementById('pDesc').innerText = data.desc;
        document.getElementById('pNumber').innerText = data.id;
        document.getElementById('pGoals').innerText = data.goals;
        document.getElementById('pAssists').innerText = data.assists;
        playerModal.classList.add('active');
        document.body.style.overflow = 'hidden';
    }

    function openMatchDetail(match) {
        document.getElementById('mdTournament').innerText = match.tournament;
        document.getElementById('mdOpponent').innerText = match.opponent;
        
        let scoreText = `${match.scorePushkar}:${match.scoreOpp}`;
        if(scoreText.includes('(')) {
            scoreText = scoreText.replace('(', '<br><span style="font-size:1rem; color:var(--text-muted); font-weight:400;">по пен. (').replace(')', ')</span>');
        }
        document.getElementById('mdScore').innerHTML = scoreText;
        
        document.getElementById('mdDate').innerText = match.date;
        document.getElementById('mdGoalscorers').innerText = match.goalscorers;
        
        closeModals(); 
        matchDetailModal.classList.add('active');
        document.body.style.overflow = 'hidden';
    }

    function openAllMatchesModal() {
        const listRoot = document.getElementById('allMatchesListRoot');
        listRoot.innerHTML = '';
        
        matchesData.forEach(m => {
            const item = document.createElement('div');
            item.className = 'list-match-card';
            item.onclick = () => openMatchDetail(m);
            item.innerHTML = `
                <div class="lmc-date">${m.date}<br><span style="font-size:0.6rem; color:var(--red);">${m.type === 'tournament' ? 'ТУРНИР' : 'ОБЫЧНЫЙ'}</span></div>
                <div class="lmc-teams">ПУШКАРЬ - ${m.opponent}</div>
                <div class="lmc-score">${m.scorePushkar}:${m.scoreOpp}</div>
            `;
            listRoot.appendChild(item);
        });

        allMatchesModal.classList.add('active');
        document.body.style.overflow = 'hidden';
    }

    // --- ЛОГИКА ВИДЕОГАЛЕРЕИ ---
    function openMediaModal() {
        renderVideoPlaylist();
        if (mediaData.length > 0) {
            selectVideo(mediaData[0].id); 
        }
        mediaModal.classList.add('active');
        document.body.style.overflow = 'hidden';
    }

    function renderVideoPlaylist() {
        const root = document.getElementById('videoPlaylistRoot');
        root.innerHTML = '';
        mediaData.forEach(v => {
            const item = document.createElement('div');
            item.className = 'playlist-item';
            item.id = `playlist-item-${v.id}`;
            item.onclick = () => selectVideo(v.id);
            item.innerHTML = `
                <div class="playlist-title">${v.title}</div>
                <div class="playlist-status">СМОТРЕТЬ</div>
            `;
            root.appendChild(item);
        });
    }

    function selectVideo(id) {
        // Обновляем визуальное отображение выбранного видео
        document.querySelectorAll('.playlist-item').forEach(el => {
            el.classList.remove('active');
            el.querySelector('.playlist-status').innerText = 'СМОТРЕТЬ';
        });
        const activeItem = document.getElementById(`playlist-item-${id}`);
        if (activeItem) {
            activeItem.classList.add('active');
            activeItem.querySelector('.playlist-status').innerText = '▶ ИГРАЕТ';
        }

        // Надежное обновление видеоплеера
        const videoInfo = mediaData.find(v => v.id === id);
        if (videoInfo) {
            const player = document.getElementById('mainVideoPlayer');
            player.src = videoInfo.src; // Присваиваем путь напрямую тегу video
            player.load();
            
            // Запуск видео с перехватом ошибки блокировки браузера
            const playPromise = player.play();
            if (playPromise !== undefined) {
                playPromise.catch(error => {
                    console.log("Автовоспроизведение заблокировано браузером или видео не найдено.");
                });
            }
        }
    }

    function closeModals() {
        modals.forEach(m => m.classList.remove('active'));
        document.body.style.overflow = '';
        
        // Автоматически ставим видео на паузу при закрытии окна
        const player = document.getElementById('mainVideoPlayer');
        if (player) {
            player.pause();
        }
    }

    window.onclick = (e) => {
        modals.forEach(m => {
            if (e.target === m) closeModals();
        });
    }
    
    // Инициализация при загрузке
    renderMatchCenter();
    renderSquad('all');
</script>

</body>
</html>
