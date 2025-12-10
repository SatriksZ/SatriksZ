<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebDev| Веб-разработка для молодежи</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Arial, sans-serif;
        }

        body {
            background: #0f172a;
            color: #f8fafc;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Навигация */
        .navbar {
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid #334155;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo-icon {
            color: #3b82f6;
            font-size: 2rem;
        }

        .logo-text {
            font-size: 1.8rem;
            font-weight: bold;
            background: linear-gradient(90deg, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 40px;
        }

        .nav-links a {
            color: #cbd5e1;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }

        .nav-links a:hover {
            color: #3b82f6;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #3b82f6;
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Герой секция */
        .hero {
            min-height: 100vh;
            padding: 150px 50px 100px;
            background: linear-gradient(135deg, rgba(15, 23, 42, 0.9), rgba(30, 41, 59, 0.9)),
                        url('https://images.unsplash.com/photo-1555066931-4365d14bab8c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .hero-content {
            max-width: 1200px;
            text-align: center;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 30px;
            background: linear-gradient(90deg, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.5rem;
            color: #cbd5e1;
            margin-bottom: 40px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 50px;
        }

        .btn-primary, .btn-secondary {
            padding: 18px 40px;
            border-radius: 50px;
            font-size: 1.2rem;
            font-weight: bold;
            text-decoration: none;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .btn-primary {
            background: linear-gradient(90deg, #3b82f6, #8b5cf6);
            color: white;
            box-shadow: 0 10px 25px rgba(59, 130, 246, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(59, 130, 246, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: #3b82f6;
            border: 2px solid #3b82f6;
        }

        .btn-secondary:hover {
            background: rgba(59, 130, 246, 0.1);
            transform: translateY(-5px);
        }

        /* Секции */
        .section {
            padding: 100px 50px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 60px;
            color: #f8fafc;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 150px;
            height: 4px;
            background: linear-gradient(90deg, #3b82f6, #8b5cf6);
            margin: 20px auto;
            border-radius: 2px;
        }

        /* О курсе */
        .course-highlights {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
            margin-bottom: 80px;
        }

        .highlight-card {
            background: rgba(30, 41, 59, 0.7);
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            border: 1px solid #475569;
            transition: all 0.3s;
        }

        .highlight-card:hover {
            transform: translateY(-10px);
            border-color: #3b82f6;
            box-shadow: 0 20px 40px rgba(59, 130, 246, 0.2);
        }

        .highlight-icon {
            font-size: 3rem;
            color: #3b82f6;
            margin-bottom: 25px;
        }

        .highlight-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #f8fafc;
        }

        .highlight-desc {
            color: #94a3b8;
            line-height: 1.6;
        }

        /* Программа обучения */
        .program-steps {
            display: flex;
            flex-direction: column;
            gap: 30px;
            max-width: 1000px;
            margin: 0 auto 80px;
        }

        .program-step {
            display: flex;
            align-items: center;
            gap: 40px;
            background: rgba(30, 41, 59, 0.5);
            border-radius: 20px;
            padding: 40px;
            border: 1px solid #475569;
            transition: all 0.3s;
        }

        .program-step:hover {
            border-color: #3b82f6;
            transform: translateX(10px);
        }

        .step-number {
            font-size: 3rem;
            font-weight: bold;
            color: #3b82f6;
            min-width: 60px;
        }

        .step-content h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: #f8fafc;
        }

        .step-content p {
            color: #94a3b8;
            line-height: 1.7;
        }

        /* Технологии */
        .technologies {
            background: rgba(30, 41, 59, 0.3);
            border-radius: 30px;
            padding: 80px 50px;
            margin-bottom: 100px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 30px;
            margin-top: 50px;
        }

        .tech-item {
            background: rgba(15, 23, 42, 0.7);
            border-radius: 15px;
            padding: 30px 20px;
            text-align: center;
            border: 1px solid #334155;
            transition: all 0.3s;
        }

        .tech-item:hover {
            transform: scale(1.1);
            border-color: #3b82f6;
            box-shadow: 0 15px 30px rgba(59, 130, 246, 0.2);
        }

        .tech-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: #3b82f6;
        }

        .tech-name {
            font-size: 1.1rem;
            font-weight: 600;
            color: #f8fafc;
        }

        /* Реклама сайта */
        .site-promo {
            background: linear-gradient(135deg, #1e40af, #7c3aed);
            border-radius: 30px;
            padding: 60px;
            margin: 100px auto;
            max-width: 1200px;
            text-align: center;
            position: relative;
            overflow: hidden;
            border: 2px solid #3b82f6;
        }

        .site-promo::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite linear;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .promo-content {
            position: relative;
            z-index: 2;
        }

        .promo-title {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: white;
        }

        .promo-text {
            font-size: 1.3rem;
            color: rgba(255, 255, 255, 0.9);
            max-width: 800px;
            margin: 0 auto 30px;
            line-height: 1.6;
        }

        /* Преимущества */
        .benefits {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 40px;
            margin-bottom: 100px;
        }

        .benefit-item {
            background: rgba(30, 41, 59, 0.7);
            border-radius: 20px;
            padding: 40px;
            border: 1px solid #475569;
            transition: all 0.3s;
        }

        .benefit-item:hover {
            border-color: #3b82f6;
            transform: translateY(-10px);
        }

        .benefit-item h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #f8fafc;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .benefit-icon {
            color: #3b82f6;
        }

        .benefit-item ul {
            list-style: none;
            margin-top: 20px;
        }

        .benefit-item li {
            color: #94a3b8;
            margin-bottom: 10px;
            padding-left: 25px;
            position: relative;
        }

        .benefit-item li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: #10b981;
            font-weight: bold;
        }

        /* Футер - ОБНОВЛЕННЫЙ */
        .footer {
            background: rgba(15, 23, 42, 0.95);
            padding: 80px 50px 40px;
            border-top: 1px solid #334155;
        }

        .footer-content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 80px;
            max-width: 1400px;
            margin: 0 auto;
            align-items: start;
        }

        .footer-info {
            max-width: 600px;
        }

        .footer-logo {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 25px;
        }

        .footer-logo-icon {
            color: #3b82f6;
            font-size: 2.5rem;
        }

        .footer-logo-text {
            font-size: 2rem;
            font-weight: bold;
            background: linear-gradient(90deg, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .footer-description {
            color: #94a3b8;
            font-size: 1.1rem;
            line-height: 1.7;
            margin-bottom: 30px;
        }

        /* Контакты - ТОЛЬКО GMAIL */
        .contacts-section {
            text-align: right;
        }

        .contacts-title {
            font-size: 1.5rem;
            margin-bottom: 30px;
            color: #f8fafc;
            text-align: left;
        }

        .contact-methods {
            display: flex;
            flex-direction: column;
            gap: 25px;
            align-items: flex-start;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
            text-decoration: none;
            color: #cbd5e1;
            transition: all 0.3s;
            padding: 12px 20px;
            border-radius: 12px;
            background: rgba(30, 41, 59, 0.5);
            border: 1px solid #475569;
            width: 100%;
            max-width: 350px;
        }

        .contact-item:hover {
            color: #3b82f6;
            border-color: #3b82f6;
            background: rgba(59, 130, 246, 0.1);
            transform: translateX(5px);
        }

        .contact-icon {
            font-size: 1.5rem;
            width: 40px;
            height: 40px;
            background: rgba(59, 130, 246, 0.1);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .contact-info {
            flex: 1;
        }

        .contact-label {
            font-size: 0.9rem;
            color: #94a3b8;
            margin-bottom: 3px;
        }

        .contact-value {
            font-size: 1.1rem;
            font-weight: 500;
            color: #f8fafc;
        }

        .social-links {
            display: flex;
            gap: 20px;
            margin-top: 40px;
            justify-content: flex-start;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 12px;
            background: rgba(30, 41, 59, 0.7);
            border: 1px solid #475569;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #cbd5e1;
            font-size: 1.3rem;
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-link:hover {
            color: #3b82f6;
            border-color: #3b82f6;
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            margin-top: 60px;
            padding-top: 40px;
            border-top: 1px solid #334155;
            color: #64748b;
            font-size: 0.9rem;
        }

        /* Адаптивность */
        @media (max-width: 1200px) {
            .course-highlights {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .tech-grid {
                grid-template-columns: repeat(4, 1fr);
            }
            
            .footer-content {
                grid-template-columns: 1fr;
                gap: 50px;
            }
            
            .contacts-section {
                text-align: left;
            }
        }

        @media (max-width: 768px) {
            .navbar {
                padding: 20px;
            }
            
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1.2rem;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .section {
                padding: 60px 20px;
            }
            
            .section-title {
                font-size: 2.2rem;
            }
            
            .course-highlights {
                grid-template-columns: 1fr;
            }
            
            .program-step {
                flex-direction: column;
                text-align: center;
                gap: 20px;
            }
            
            .tech-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .benefits {
                grid-template-columns: 1fr;
            }
            
            .site-promo {
                padding: 40px 20px;
                margin: 50px 20px;
            }
            
            .contact-item {
                max-width: 100%;
            }
        }
    </style>
</head>
<body>
    <!-- Навигация -->
    <nav class="navbar">
        <div class="logo">
            <i class="fas fa-code logo-icon"></i>
            <div class="logo-text">WebDev</div>
        </div>
        <div class="nav-links">
            <a href="#about">О курсе</a>
            <a href="#program">Программа</a>
            <a href="#tech">Технологии</a>
            <a href="#benefits">Преимущества</a>
        
        </div>
    </nav>

    <!-- Герой секция -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>СТАНЬ ВЕБ-РАЗРАБОТЧИКОМ<br>С НУЛЯ</h1>
            <p>Практическое обучение для молодежи. Создавай реальные проекты, строй карьеру в IT и зарабатывай на своих навыках.</p>
           
                </a>
            </div>
        </div>
    </section>

    <!-- О курсе -->
    <section class="section" id="about">
        <h2 class="section-title">ЧТО ТЫ ПОЛУЧИШЬ НА КУРСЕ</h2>
        <div class="course-highlights">
            <div class="highlight-card">
                <i class="fas fa-laptop-code highlight-icon"></i>
                <h3 class="highlight-title">Полный стек технологий</h3>
                <p class="highlight-desc">От HTML/CSS до React и Node.js. Изучи все инструменты современного разработчика.</p>
            </div>
            <div class="highlight-card">
                <i class="fas fa-briefcase highlight-icon"></i>
                <h3 class="highlight-title">Карьерный рост</h3>
                <p class="highlight-desc">Помощь в трудоустройстве, стажировки в IT-компаниях и поддержка менторов.</p>
            </div>
            <div class="highlight-card">
                <i class="fas fa-project-diagram highlight-icon"></i>
                <h3 class="highlight-title">Реальные проекты</h3>
                <p class="highlight-desc">Создай 5+ проектов для портфолио: от лендингов до полноценных веб-приложений.</p>
            </div>
        </div>
    </section>

    <!-- Программа обучения -->
    <section class="section" id="program">
        <h2 class="section-title">ПРОГРАММА ОБУЧЕНИЯ</h2>
        <div class="program-steps">
            <div class="program-step">
                <div class="step-number">01</div>
                <div class="step-content">
                    <h3>Основы веб-разработки</h3>
                    <p>HTML5, CSS3, JavaScript ES6+. Создание адаптивных сайтов, работа с DOM, основы программирования. Первые проекты в портфолио.</p>
                </div>
            </div>
            <div class="program-step">
                <div class="step-number">02</div>
                <div class="step-content">
                    <h3>Frontend разработка</h3>
                    <p>React.js, Vue.js, TypeScript. Современные фреймворки, управление состоянием, работа с API. Создание SPA-приложений.</p>
                </div>
            </div>
            <div class="program-step">
                <div class="step-number">03</div>
                <div class="step-content">
                    <h3>Backend разработка</h3>
                    <p>Node.js, Express, базы данных (MongoDB, PostgreSQL). Создание серверов, REST API, аутентификация и авторизация.</p>
                </div>
            </div>
            <div class="program-step">
                <div class="step-number">04</div>
                <div class="step-content">
                    <h3>Fullstack проекты</h3>
                    <p>Командная разработка, DevOps основы, деплой проектов. Дипломная работа - полноценное веб-приложение.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Технологии -->
    <section class="section" id="tech">
        <h2 class="section-title">ТЕХНОЛОГИИ КОТОРЫЕ ТЫ ИЗУЧИШЬ</h2>
        <div class="technologies">
            <div class="tech-grid">
                <div class="tech-item">
                    <i class="fab fa-html5 tech-icon"></i>
                    <div class="tech-name">HTML5</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-css3-alt tech-icon"></i>
                    <div class="tech-name">CSS3</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-js-square tech-icon"></i>
                    <div class="tech-name">JavaScript</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-react tech-icon"></i>
                    <div class="tech-name">React</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-node-js tech-icon"></i>
                    <div class="tech-name">Node.js</div>
                </div>
                <div class="tech-item">
                    <i class="fas fa-database tech-icon"></i>
                    <div class="tech-name">MongoDB</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-git-alt tech-icon"></i>
                    <div class="tech-name">Git</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-docker tech-icon"></i>
                    <div class="tech-name">Docker</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-vuejs tech-icon"></i>
                    <div class="tech-name">Vue.js</div>
                </div>
                <div class="tech-item">
                    <i class="fab fa-python tech-icon"></i>
                    <div class="tech-name">Python</div>
                </div>
                <div class="tech-item">
                    <i class="fas fa-server tech-icon"></i>
                    <div class="tech-name">Express</div>
                </div>
                <div class="tech-item">
                    <i class="fas fa-mobile-alt tech-icon"></i>
                    <div class="tech-name">PWA</div>
                </div>
            </div>
        </div>
    </section>



    <!-- Преимущества -->
    <section class="section" id="benefits">
        <h2 class="section-title">ПОЧЕМУ ВЫБИРАЮТ НАС</h2>
        <div class="benefits">
            <div class="benefit-item">
                <h3><i class="fas fa-user-graduate benefit-icon"></i> Для начинающих</h3>
                <p>Обучение с нуля, без технического бэкграунда. Пошаговые инструкции и поддержка на каждом этапе.</p>
                <ul>
                    <li>Начинаем с самых основ</li>
                    <li>Понятные объяснения</li>
                    <li>Постоянная поддержка</li>
                </ul>
            </div>
            <div class="benefit-item">
                <h3><i class="fas fa-chart-line benefit-icon"></i> Результат</h3>
                <p>92% выпускников находят работу в течение 6 месяцев после окончания курса.</p>
                <ul>
                    <li>Средняя зарплата: 85,000₽</li>
                    <li>Помощь с резюме и собеседованиями</li>
                </ul>
            
          
    </section>

    <!-- Футер - ОБНОВЛЕННЫЙ (только Telegram и Gmail) -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-info">
                <div class="footer-logo">
                    <i class="fas fa-code footer-logo-icon"></i>
                    <div class="footer-logo-text">WebDev</div>
                </div>
                <p class="footer-description">
                    Веб-разработка для молодежи
                
                    </a>
                </div>
            </div>
            
          
                    
                    <a href="mailto:dimasaltykov79@gmail.com" class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-info">
                            <div class="contact-label">Email для связи</div>
                            <div class="contact-value">dimasaltykov79@gmail.com</div>
                        </div>
                    </a>
                </div>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>© 2024 WebDev. Веб-разработка для молодежи.</p>
            <p style="margin-top: 10px; font-size: 0.85rem; color: #94a3b8;">
                Начни свой путь в IT сегодня. Обучение с нуля, поддержка 24/7, гарантия трудоустройства.
            </p>
        </div>
    </footer>

    <script>
      
    </script>
</body>
</html>
