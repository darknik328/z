<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>SecureWeb | Разработка сайтов с кибербезопасностью</title>
    <!-- Google Fonts & Font Awesome -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #f8fafc;
            color: #0a0f1e;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        /* modern container */
        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        /* header & navigation */
        header {
            background: #0a0f1e;
            color: white;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.1);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 1.7rem;
            font-weight: 800;
            letter-spacing: -0.5px;
        }
        .logo span {
            color: #3b82f6;
        }
        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }
        .nav-links a {
            color: #e2e8f0;
            text-decoration: none;
            font-weight: 500;
            transition: 0.2s;
        }
        .nav-links a:hover, .nav-links a.active {
            color: #3b82f6;
        }
        .mobile-menu {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
        }

        /* hero section */
        .hero {
            background: linear-gradient(135deg, #0a0f1e 0%, #10172b 100%);
            color: white;
            padding: 5rem 0;
        }
        .hero .container {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 3rem;
        }
        .hero-content {
            flex: 1.2;
        }
        .hero-badge {
            background: #1e293b;
            display: inline-block;
            padding: 0.3rem 1rem;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            color: #94a3b8;
            margin-bottom: 1.2rem;
        }
        .hero-content h1 {
            font-size: 3.2rem;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 1.5rem;
        }
        .hero-content p {
            font-size: 1.2rem;
            color: #cbd5e1;
            max-width: 550px;
            margin-bottom: 2rem;
        }
        .btn-group {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }
        .btn-primary, .btn-outline {
            padding: 0.8rem 2rem;
            border-radius: 40px;
            font-weight: 600;
            transition: 0.2s;
            text-decoration: none;
            display: inline-block;
        }
        .btn-primary {
            background: #3b82f6;
            color: white;
            border: none;
        }
        .btn-primary:hover {
            background: #2563eb;
            transform: translateY(-2px);
        }
        .btn-outline {
            border: 1px solid #3b82f6;
            color: #3b82f6;
            background: transparent;
        }
        .btn-outline:hover {
            background: #3b82f610;
            border-color: #60a5fa;
        }
        .hero-stats {
            flex: 1;
            background: rgba(255,255,255,0.03);
            backdrop-filter: blur(4px);
            border-radius: 2rem;
            padding: 1.8rem;
            border: 1px solid #1e293b;
        }
        .stat-item {
            margin: 1rem 0;
        }
        .stat-number {
            font-size: 2rem;
            font-weight: 800;
            color: #3b82f6;
        }

        /* cards / grid sections */
        .section {
            padding: 5rem 0;
        }
        .section-title {
            font-size: 2.2rem;
            font-weight: 800;
            text-align: center;
            margin-bottom: 3rem;
        }
        .section-sub {
            text-align: center;
            color: #475569;
            max-width: 700px;
            margin: -1rem auto 3rem auto;
        }
        .grid-3 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        .card {
            background: white;
            border-radius: 1.5rem;
            padding: 2rem;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.05);
            transition: all 0.25s ease;
            border: 1px solid #eef2ff;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 30px -12px rgba(0,0,0,0.1);
            border-color: #cbd5e1;
        }
        .card-icon {
            font-size: 2.5rem;
            color: #3b82f6;
            margin-bottom: 1.2rem;
        }
        .card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }
        .card p {
            color: #334155;
        }

        /* security table / checklist */
        .checklist {
            background: #ffffff;
            border-radius: 1.5rem;
            box-shadow: 0 4px 14px rgba(0,0,0,0.03);
            overflow: hidden;
            border: 1px solid #e2e8f0;
        }
        .checklist-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.2rem 2rem;
            border-bottom: 1px solid #f1f5f9;
            transition: background 0.1s;
        }
        .checklist-item:last-child {
            border-bottom: none;
        }
        .checklist-icon {
            width: 32px;
            color: #10b981;
            font-size: 1.3rem;
        }
        .checklist-text strong {
            display: block;
            font-size: 1.1rem;
        }

        /* process steps */
        .steps {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: space-between;
        }
        .step {
            flex: 1;
            min-width: 200px;
            background: white;
            padding: 1.8rem;
            border-radius: 1.5rem;
            text-align: center;
            border: 1px solid #eef2ff;
        }
        .step-number {
            width: 50px;
            height: 50px;
            background: #3b82f6;
            color: white;
            font-weight: 800;
            font-size: 1.5rem;
            border-radius: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem auto;
        }

        /* footer */
        footer {
            background: #0a0f1e;
            color: #94a3b8;
            padding: 3rem 0 2rem;
            margin-top: 2rem;
        }
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        .footer-col h4 {
            color: white;
            margin-bottom: 1rem;
        }
        .footer-col a {
            color: #94a3b8;
            text-decoration: none;
            display: block;
            margin: 0.5rem 0;
        }
        .copyright {
            text-align: center;
            border-top: 1px solid #1e293b;
            padding-top: 2rem;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                width: 100%;
                flex-direction: column;
                text-align: center;
                padding: 1rem 0;
            }
            .nav-links.active {
                display: flex;
            }
            .mobile-menu {
                display: block;
            }
            .hero-content h1 {
                font-size: 2.2rem;
            }
            .container {
                padding: 0 1.5rem;
            }
        }
        button {
            background: none;
            border: none;
        }
    </style>
</head>
<body>

<!-- Многостраничная логика: 4 "страницы" через скрытые блоки + активная навигация -->
<header>
    <div class="navbar">
        <div class="logo">Secure<span>Web</span></div>
        <div class="mobile-menu" id="mobileMenuBtn">
            <i class="fas fa-bars"></i>
        </div>
        <ul class="nav-links" id="navLinks">
            <li><a href="#" data-page="home" class="active">Главная</a></li>
            <li><a href="#" data-page="security">Кибербезопасность</a></li>
            <li><a href="#" data-page="process">Процесс разработки</a></li>
            <li><a href="#" data-page="resources">Ресурсы & стандарты</a></li>
        </ul>
    </div>
</header>

<main id="app">
    <!-- СТРАНИЦА 1: ГЛАВНАЯ / РАЗРАБОТКА + ОБЗОР -->
    <div id="page-home" class="page-content">
        <section class="hero">
            <div class="container">
                <div class="hero-content">
                    <div class="hero-badge"><i class="fas fa-shield-alt"></i>  Защищённая разработка</div>
                    <h1>Разработка веб-сайтов с нулевым доверием к угрозам</h1>
                    <p>Создаём надёжные, производительные и безопасные веб-решения. Интеграция киберзащиты на каждом этапе: от кода до DevSecOps.</p>
                    <div class="btn-group">
                        <a href="#" class="btn-primary" data-page="security">🔒 Изучить безопасность</a>
                        <a href="#" class="btn-outline" data-page="process">📐 Процесс разработки</a>
                    </div>
                </div>
                <div class="hero-stats">
                    <div class="stat-item"><span class="stat-number">99.9%</span> <br> uptime с защитой</div>
                    <div class="stat-item"><span class="stat-number">0 уязвимостей</span> <br> при аудитах high-risk</div>
                    <div class="stat-item"><span class="stat-number">ISO 27001</span> <br> соответствие стандартам</div>
                </div>
            </div>
        </section>
        
        <section class="section">
            <div class="container">
                <h2 class="section-title">Безопасность в каждой строке кода</h2>
                <div class="grid-3">
                    <div class="card">
                        <div class="card-icon"><i class="fas fa-lock"></i></div>
                        <h3>Безопасный SDLC</h3>
                        <p>Мы внедряем этапы Threat Modeling, SAST/DAST сканирование и аудит зависимостей, чтобы предупредить атаки на этапе разработки.</p>
                    </div>
                    <div class="card">
                        <div class="card-icon"><i class="fas fa-database"></i></div>
                        <h3>Шифрование данных</h3>
                        <p>TLS 1.3, шифрование бэкапов, хеширование паролей (bcrypt/Argon2) и защита PII соответствуют GDPR и российским требованиям.</p>
                    </div>
                    <div class="card">
                        <div class="card-icon"><i class="fas fa-shield-virus"></i></div>
                        <h3>WAF & DDoS защита</h3>
                        <p>Настройка Web Application Firewall, rate limiting, защита от OWASP Top 10, включая SQLi, XSS и CSRF атаки.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="section" style="background: #eef2ff40;">
            <div class="container">
                <h2 class="section-title">Почему кибербезопасность — основа современного веба?</h2>
                <div class="grid-3">
                    <div class="card"><i class="fas fa-chart-line card-icon"></i><h3>Репутация & доверие</h3><p>53% пользователей покидают сайт после утечки данных. Защита сохраняет бизнес.</p></div>
                    <div class="card"><i class="fas fa-gavel card-icon"></i><h3>Законодательство</h3><p>Соответствие 152-ФЗ, PCI DSS и HIPAA требует защищённой архитектуры.</p></div>
                    <div class="card"><i class="fas fa-bug card-icon"></i><h3>Устойчивость к атакам</h3><p>Ежедневно более 30 000 веб-сайтов взламываются. Проактивная защита обязательна.</p></div>
                </div>
            </div>
        </section>
    </div>

    <!-- СТРАНИЦА 2: КИБЕРБЕЗОПАСНОСТЬ (детально) -->
    <div id="page-security" class="page-content" style="display: none;">
        <section class="hero" style="background: #0c1a2f; padding: 3rem 0;">
            <div class="container">
                <h1 style="font-size: 2.5rem;">Кибербезопасность веб-проектов</h1>
                <p>Комплексная стратегия защиты: от разведки угроз до мониторинга инцидентов 24/7.</p>
            </div>
        </section>

        <section class="section">
            <div class="container">
                <h2 class="section-title">🔐 Основные практики безопасности</h2>
                <div class="checklist">
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-check-circle"></i></div><div class="checklist-text"><strong>Валидация и санитизация входных данных</strong><span>Защита от инъекций и XSS через строгую фильтрацию.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-check-circle"></i></div><div class="checklist-text"><strong>CSP, HSTS и безопасные заголовки</strong><span>Настройка Content-Security-Policy, Strict-Transport-Security, X-Frame-Options.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-check-circle"></i></div><div class="checklist-text"><strong>Аутентификация MFA & управление сессиями</strong><span>Реализация JWT с коротким TTL, refresh-токены и защита от session fixation.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-check-circle"></i></div><div class="checklist-text"><strong>Регулярные пентесты и сканирование уязвимостей</strong><span>Ежеквартальный аудит с отчётом и исправлением.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-check-circle"></i></div><div class="checklist-text"><strong>Безопасное хранение секретов</strong><span>Vault / environment variables, никаких паролей в коде.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-check-circle"></i></div><div class="checklist-text"><strong>Автоматизация обновлений зависимостей</strong><span>Dependabot, Snyk — мониторинг CVE.</span></div></div>
                </div>
            </div>
        </section>

        <section class="section" style="background: #f1f5f9;">
            <div class="container">
                <h2 class="section-title">Типовые веб-угрозы и методы защиты</h2>
                <div class="grid-3">
                    <div class="card"><i class="fas fa-terminal card-icon"></i><h3>SQL Injection</h3><p>Использование параметризованных запросов (Prepared Statements), ORM и WAF правил.</p></div>
                    <div class="card"><i class="fas fa-code card-icon"></i><h3>XSS (Cross-Site Scripting)</h3><p>Экранирование вывода, CSP без 'unsafe-inline', HttpOnly куки.</p></div>
                    <div class="card"><i class="fas fa-crosshairs card-icon"></i><h3>CSRF</h3><p>Anti-CSRF токены, SameSite cookies, проверка Referer.</p></div>
                    <div class="card"><i class="fas fa-unlock-alt card-icon"></i><h3>Broken Access Control</h3><p>RBAC модели, тестирование на горизонтальное/вертикальное повышение прав.</p></div>
                    <div class="card"><i class="fas fa-cloud-upload-alt card-icon"></i><h3>SSRF</h3><p>Валидация входящих URL, белые списки, сетевые политики.</p></div>
                    <div class="card"><i class="fas fa-tachometer-alt card-icon"></i><h3>DoS / Slowloris</h3><p>Rate limiting, reverse-proxy с лимитами, CDN и анализ трафика.</p></div>
                </div>
            </div>
        </section>
    </div>

    <!-- СТРАНИЦА 3: ПРОЦЕСС РАЗРАБОТКИ -->
    <div id="page-process" class="page-content" style="display: none;">
        <section class="hero" style="background: #0b1120;">
            <div class="container">
                <h1>Жизненный цикл безопасной разработки</h1>
                <p>Secure SDLC + Agile + DevSecOps — строим веб-проекты с защитой "по умолчанию".</p>
            </div>
        </section>
        <section class="section">
            <div class="container">
                <div class="steps">
                    <div class="step"><div class="step-number">1</div><h3>Анализ требований</h3><p>Моделирование угроз, определение активов и границ безопасности.</p></div>
                    <div class="step"><div class="step-number">2</div><h3>Проектирование</h3><p>Архитектура с принципами наименьших привилегий, threat modelling (STRIDE).</p></div>
                    <div class="step"><div class="step-number">3</div><h3>Разработка</h3><p>Безопасные coding practices, pre-commit хуки, SAST (SonarQube).</p></div>
                    <div class="step"><div class="step-number">4</div><h3>Тестирование</h3><p>DAST, интерактивное тестирование (IAST), пентест.</p></div>
                    <div class="step"><div class="step-number">5</div><h3>Деплой & мониторинг</h3><p>CI/CD с проверкой образов, SIEM, логирование инцидентов.</p></div>
                </div>
            </div>
        </section>
        <section class="section" style="background: #ffffff;">
            <div class="container">
                <h2 class="section-title">📊 Инструменты DevSecOps</h2>
                <div class="grid-3">
                    <div class="card"><i class="fab fa-github card-icon"></i><h3>GitHub Advanced Security</h3><p>CodeQL, secret scanning, dependency review в экосистеме CI/CD.</p></div>
                    <div class="card"><i class="fas fa-chalkboard-teacher card-icon"></i><h3>OWASP ZAP / Burp Suite</h3><p>Автоматизированное DAST сканирование на каждом релизе.</p></div>
                    <div class="card"><i class="fas fa-infinity card-icon"></i><h3>Terraform + Checkov</h3><p>IaC сканирование на предмет ошибок конфигурации облачной инфраструктуры.</p></div>
                </div>
            </div>
        </section>
    </div>

    <!-- СТРАНИЦА 4: РЕСУРСЫ И СТАНДАРТЫ -->
    <div id="page-resources" class="page-content" style="display: none;">
        <section class="hero" style="background: #0a0f1e; padding: 3rem 0;">
            <div class="container">
                <h1>Стандарты, нормативы и знания</h1>
                <p>Актуальные фреймворки и лучшие практики от NIST, OWASP и ISO.</p>
            </div>
        </section>
        <section class="section">
            <div class="container">
                <div class="grid-3">
                    <div class="card"><i class="fas fa-shield-alt card-icon"></i><h3>OWASP Top 10 2025</h3><p>Актуальный перечень критических рисков веб-приложений — фундамент безопасности.</p></div>
                    <div class="card"><i class="fas fa-certificate card-icon"></i><h3>ISO/IEC 27001</h3><p>Система менеджмента информационной безопасности для сертификации процессов.</p></div>
                    <div class="card"><i class="fas fa-chart-network card-icon"></i><h3>NIST Cybersecurity Framework</h3><p>Рекомендации по идентификации, защите, обнаружению и восстановлению.</p></div>
                    <div class="card"><i class="fas fa-book card-icon"></i><h3>PCI DSS v4.0</h3><p>Стандарт безопасности данных платёжных карт для e-commerce.</p></div>
                    <div class="card"><i class="fas fa-user-secret card-icon"></i><h3>GDPR / 152-ФЗ</h3><p>Обеспечение конфиденциальности персональных данных и права субъектов.</p></div>
                    <div class="card"><i class="fas fa-tasks card-icon"></i><h3>MITRE ATT&CK для веба</h3><p>Тактики и техники злоумышленников, эмуляция угроз.</p></div>
                </div>
            </div>
        </section>
        <section class="section" style="background: #f8fafc;">
            <div class="container">
                <h2 class="section-title">Обучение и рост команды</h2>
                <div class="checklist">
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-graduation-cap"></i></div><div class="checklist-text"><strong>Secure coding training</strong><span>Регулярные воркшопы для разработчиков.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-flag-checkered"></i></div><div class="checklist-text"><strong>Bug bounty программы</strong><span>Привлечение исследователей для поиска уязвимостей.</span></div></div>
                    <div class="checklist-item"><div class="checklist-icon"><i class="fas fa-chalkboard"></i></div><div class="checklist-text"><strong>Красные команды / Purple team</strong><span>Имитация реальных атак для улучшения защиты.</span></div></div>
                </div>
            </div>
        </section>
    </div>
</main>

<footer>
    <div class="container">
        <div class="footer-grid">
            <div class="footer-col"><h4>SecureWeb</h4><p>Интеграция кибербезопасности в жизненный цикл веб-разработки. Защита данных, аудит, соответствие стандартам.</p></div>
            <div class="footer-col"><h4>Разделы</h4><a href="#" data-page="home">Главная</a><a href="#" data-page="security">Кибербезопасность</a><a href="#" data-page="process">Процесс разработки</a><a href="#" data-page="resources">Ресурсы</a></div>
            <div class="footer-col"><h4>Контакты</h4><a href="#">security@secureweb.ru</a><a href="#">+7 (495) 123-45-67</a><a href="#"><i class="fab fa-telegram"></i> Telegram канал</a></div>
        </div>
        <div class="copyright">© 2025 SecureWeb — разработка веб-сайтов с гарантией безопасности. Все права защищены.</div>
    </div>
</footer>

<script>
    // Многостраничная навигация + мобильное меню
    const pages = ['home', 'security', 'process', 'resources'];
    function showPage(pageId) {
        pages.forEach(p => {
            const el = document.getElementById(`page-${p}`);
            if(el) el.style.display = 'none';
        });
        const activePage = document.getElementById(`page-${pageId}`);
        if(activePage) activePage.style.display = 'block';

        // обновляем активный класс в навигации
        document.querySelectorAll('.nav-links a').forEach(link => {
            const linkPage = link.getAttribute('data-page');
            if(linkPage === pageId) {
                link.classList.add('active');
            } else {
                link.classList.remove('active');
            }
        });
        // также обновить активные ссылки в футере
        document.querySelectorAll('footer a[data-page]').forEach(link => {
            // ничего страшного, просто ссылки
        });
        // scroll to top
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // обработчики для всех навигационных ссылок
    function bindNavEvents() {
        const navLinks = document.querySelectorAll('.nav-links a, footer a[data-page], .btn-group a[data-page]');
        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                const page = link.getAttribute('data-page');
                if(page && pages.includes(page)) {
                    e.preventDefault();
                    showPage(page);
                    // если мобильное меню открыто, закрываем
                    const mobileNav = document.getElementById('navLinks');
                    if(mobileNav.classList.contains('active')) {
                        mobileNav.classList.remove('active');
                    }
                }
            });
        });
        // также обработать кнопки в hero
        const heroBtns = document.querySelectorAll('.btn-primary, .btn-outline');
        heroBtns.forEach(btn => {
            if(btn.getAttribute('data-page')) {
                btn.addEventListener('click', (e) => {
                    const page = btn.getAttribute('data-page');
                    if(page && pages.includes(page)) {
                        e.preventDefault();
                        showPage(page);
                    }
                });
            }
        });
    }

    // mobile menu toggle
    const mobileBtn = document.getElementById('mobileMenuBtn');
    const navUl = document.getElementById('navLinks');
    if(mobileBtn) {
        mobileBtn.addEventListener('click', () => {
            navUl.classList.toggle('active');
        });
    }

    // начальная загрузка (home)
    showPage('home');
    bindNavEvents();
    
    // дополнительно: перехватываем все ссылки с data-page в динамически добавленных (но у нас статика)
    document.body.addEventListener('click', (e) => {
        let target = e.target.closest('[data-page]');
        if(target && target.getAttribute('data-page') && pages.includes(target.getAttribute('data-page'))) {
            e.preventDefault();
            showPage(target.getAttribute('data-page'));
            if(navUl.classList.contains('active')) navUl.classList.remove('active');
        }
    });
</script>
</body>
</html>
