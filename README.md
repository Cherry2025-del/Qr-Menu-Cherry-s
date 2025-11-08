
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cherry's - Fast Food</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-red: #e50914;
            --dark-red: #b20710;
            --white: #ffffff;
            --black: #1a1a1a;
            --gray: #f5f5f5;
        }

        body {
            font-family: 'Poppins', sans-serif;
            overflow-x: hidden;
            background: var(--black);
            color: var(--white);
        }

        /* Page d'accueil */
        .home-page {
            min-height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), 
                        url('https://images.unsplash.com/photo-1568901346375-23c9450c58cd?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            animation: fadeIn 1s ease-in;
        }

        .logo-container {
            position: absolute;
            top: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: slideDown 0.8s ease-out;
        }

        .logo {
            font-size: 3rem;
            font-weight: 700;
            color: var(--primary-red);
            text-shadow: 3px 3px 6px rgba(0,0,0,0.7);
            letter-spacing: 2px;
        }

        .logo span {
            color: var(--white);
        }

        .menu-button {
            font-size: 4rem;
            font-weight: 700;
            color: var(--white);
            background: var(--primary-red);
            padding: 30px 60px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(229, 9, 20, 0.4);
            animation: pulse 2s infinite;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .menu-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(229, 9, 20, 0.6);
            background: var(--dark-red);
        }

        /* Page des familles */
        .families-page {
            min-height: 100vh;
            background: var(--gray);
            padding: 80px 20px;
            display: none;
            animation: fadeIn 0.5s ease-in;
        }

        .families-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .family-card {
            background: var(--white);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
        }

        .family-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .family-image {
            width: 100%;
            height: 200px;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .family-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.8), transparent);
            display: flex;
            align-items: flex-end;
            padding: 20px;
        }

        .family-title {
            color: var(--white);
            font-size: 1.8rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Page de détails */
        .details-page {
            min-height: 100vh;
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            display: none;
            animation: fadeIn 0.5s ease-in;
            position: relative;
        }

        .details-overlay {
            background: rgba(0,0,0,0.9);
            min-height: 100vh;
            padding: 80px 20px;
        }

        .details-container {
            max-width: 1000px;
            margin: 0 auto;
            background: var(--white);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
        }

        .page-title {
            color: var(--primary-red);
            font-size: 3rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 40px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .items-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .item-card {
            background: var(--gray);
            border-radius: 15px;
            padding: 20px;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .item-card:hover {
            transform: scale(1.05);
            border-color: var(--primary-red);
            box-shadow: 0 10px 30px rgba(229, 9, 20, 0.2);
        }

        .item-name {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--black);
            margin-bottom: 10px;
        }

        .item-price {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-red);
            margin-top: 10px;
        }

        .whatsapp-button {
            display: inline-block;
            background: #25d366;
            color: var(--white);
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(37, 211, 102, 0.3);
            text-align: center;
            margin: 20px auto;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            max-width: 300px;
        }

        .whatsapp-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.5);
        }

        .back-button {
            position: absolute;
            top: 20px;
            left: 20px;
            background: var(--primary-red);
            color: var(--white);
            border: none;
            padding: 10px 20px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
            z-index: 100;
        }

        .back-button:hover {
            background: var(--dark-red);
            transform: translateX(-5px);
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideDown {
            from { 
                opacity: 0;
                transform: translateX(-50%) translateY(-50px);
            }
            to { 
                opacity: 1;
                transform: translateX(-50%) translateY(0);
            }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .logo {
                font-size: 2rem;
            }
            
            .menu-button {
                font-size: 2.5rem;
                padding: 20px 40px;
            }
            
            .families-container {
                grid-template-columns: 1fr;
            }
            
            .page-title {
                font-size: 2rem;
            }
            
            .items-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Page d'accueil -->
    <div class="home-page" id="homePage">
        <div class="logo-container">
            <div class="logo">CHERRY'S</div>
        </div>
        <button class="menu-button" onclick="showFamilies()">Menu</button>
    </div>

    <!-- Page des familles -->
    <div class="families-page" id="familiesPage">
        <button class="back-button" onclick="showHome()">
            <i class="fas fa-arrow-left"></i> Accueil
        </button>
        <div class="families-container">
            <div class="family-card" onclick="showDetails('fastfood')">
                <div class="family-image" style="background-image: url('https://images.unsplash.com/photo-1565299507177-b0ac66763828?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
                    <div class="family-overlay">
                        <h3 class="family-title">Fast-food</h3>
                    </div>
                </div>
            </div>
            
            <div class="family-card" onclick="showDetails('pizzas')">
                <div class="family-image" style="background-image: url('https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
                    <div class="family-overlay">
                        <h3 class="family-title">Pizzas</h3>
                    </div>
                </div>
            </div>
            
            <div class="family-card" onclick="showDetails('grillades')">
                <div class="family-image" style="background-image: url('https://images.unsplash.com/photo-1546833999-b9f581a1996d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
                    <div class="family-overlay">
                        <h3 class="family-title">Grillades</h3>
                    </div>
                </div>
            </div>
            
            <div class="family-card" onclick="showDetails('mixtes')">
                <div class="family-image" style="background-image: url('https://images.unsplash.com/photo-1555939594-58d7cb561ad1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
                    <div class="family-overlay">
                        <h3 class="family-title">Mixtes à partager</h3>
                    </div>
                </div>
            </div>
            
            <div class="family-card" onclick="showDetails('glaces')">
                <div class="family-image" style="background-image: url('https://images.unsplash.com/photo-1559703445-31441a1714b6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
                    <div class="family-overlay">
                        <h3 class="family-title">Glaces</h3>
                    </div>
                </div>
            </div>
            
            <div class="family-card" onclick="showDetails('boissons')">
                <div class="family-image" style="background-image: url('https://images.unsplash.com/photo-1544145945-f90425340c7e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
                    <div class="family-overlay">
                        <h3 class="family-title">Boissons</h3>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Page de détails Fast-food -->
    <div class="details-page" id="fastfoodPage" style="background-image: url('https://images.unsplash.com/photo-1565299507177-b0ac66763828?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
        <div class="details-overlay">
            <button class="back-button" onclick="showFamilies()">
                <i class="fas fa-arrow-left"></i> Retour
            </button>
            <div class="details-container">
                <h2 class="page-title">Fast-food</h2>
                <div class="items-grid">
                    <div class="item-card">
                        <div class="item-name">Gyros au poulet</div>
                        <div class="item-price">3000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Gyros au bœuf</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Gyros cherry's</div>
                        <div class="item-price">4500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Sandwich viande</div>
                        <div class="item-price">1000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Sandwich poulet</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Chawarma poulet</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Chawarma viande</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Hamburger</div>
                        <div class="item-price">2500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Chiken burgers</div>
                        <div class="item-price">3000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Cherry's burgers</div>
                        <div class="item-price">4000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">KFC</div>
                        <div class="item-price">4000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Plat de Nems 4 pièces</div>
                        <div class="item-price">2500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Tacos viande</div>
                        <div class="item-price">2500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Tacos poulet</div>
                        <div class="item-price">3500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Tacos cherry's</div>
                        <div class="item-price">4500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Big Sandwich</div>
                        <div class="item-price">8000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Big burgers</div>
                        <div class="item-price">6000f</div>
                    </div>
                </div>
                <a href="https://wa.me/22384124748" class="whatsapp-button" target="_blank">
                    <i class="fab fa-whatsapp"></i> Commander sur WhatsApp
                </a>
            </div>
        </div>
    </div>

    <!-- Page Pizzas -->
    <div class="details-page" id="pizzasPage" style="background-image: url('https://images.unsplash.com/photo-1565299624946-b28f40a0ae38?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
        <div class="details-overlay">
            <button class="back-button" onclick="showFamilies()">
                <i class="fas fa-arrow-left"></i> Retour
            </button>
            <div class="details-container">
                <h2 class="page-title">Pizzas</h2>
                <div class="items-grid">
                    <div class="item-card">
                        <div class="item-name">Pizza cherry's</div>
                        <div class="item-price">7000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Pizza margarita</div>
                        <div class="item-price">5000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Pizza orientale</div>
                        <div class="item-price">6000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Pizza végétarien</div>
                        <div class="item-price">6000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Pizza Kiss</div>
                        <div class="item-price">6500f</div>
                    </div>
                </div>
                <a href="https://wa.me/22384124748" class="whatsapp-button" target="_blank">
                    <i class="fab fa-whatsapp"></i> Commander sur WhatsApp
                </a>
            </div>
        </div>
    </div>

    <!-- Page Grillades -->
    <div class="details-page" id="grilladesPage" style="background-image: url('https://images.unsplash.com/photo-1546833999-b9f581a1996d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
        <div class="details-overlay">
            <button class="back-button" onclick="showFamilies()">
                <i class="fas fa-arrow-left"></i> Retour
            </button>
            <div class="details-container">
                <h2 class="page-title">Grillades</h2>
                <div class="items-grid">
                    <div class="item-card">
                        <div class="item-name">Brochette de bœuf</div>
                        <div class="item-price">6000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Brochette de poulet</div>
                        <div class="item-price">6000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Brochette de capitaine</div>
                        <div class="item-price">7000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">1/2 poulet</div>
                        <div class="item-price">6000f</div>
                    </div>
                </div>
                <a href="https://wa.me/22384124748" class="whatsapp-button" target="_blank">
                    <i class="fab fa-whatsapp"></i> Commander sur WhatsApp
                </a>
            </div>
        </div>
    </div>

    <!-- Page Mixtes -->
    <div class="details-page" id="mixtesPage" style="background-image: url('https://images.unsplash.com/photo-1555939594-58d7cb561ad1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
        <div class="details-overlay">
            <button class="back-button" onclick="showFamilies()">
                <i class="fas fa-arrow-left"></i> Retour
            </button>
            <div class="details-container">
                <h2 class="page-title">Mixtes à partager</h2>
                <div class="items-grid">
                    <div class="item-card">
                        <div class="item-name">Mixte fast-food</div>
                        <div class="item-price">15000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Mixte grillé</div>
                        <div class="item-price">15000f</div>
                    </div>
                </div>
                <a href="https://wa.me/22384124748" class="whatsapp-button" target="_blank">
                    <i class="fab fa-whatsapp"></i> Commander sur WhatsApp
                </a>
            </div>
        </div>
    </div>

    <!-- Page Glaces -->
    <div class="details-page" id="glacesPage" style="background-image: url('https://images.unsplash.com/photo-1559703445-31441a1714b6?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
        <div class="details-overlay">
            <button class="back-button" onclick="showFamilies()">
                <i class="fas fa-arrow-left"></i> Retour
            </button>
            <div class="details-container">
                <h2 class="page-title">Glaces</h2>
                <div class="items-grid">
                    <div class="item-card">
                        <div class="item-name">Une boule</div>
                        <div class="item-price">1000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Deux boules</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Trois boules</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Cornet 2 boules</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Cornet 3 boules</div>
                        <div class="item-price">2500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Cornet Américain 1 boule</div>
                        <div class="item-price">1000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Cornet Américain 2 boules</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Wafeles bowls 1 boule</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Wafeles bowls 2 boules</div>
                        <div class="item-price">2500f</div>
                    </div>
                </div>
                <a href="https://wa.me/22384124748" class="whatsapp-button" target="_blank">
                    <i class="fab fa-whatsapp"></i> Commander sur WhatsApp
                </a>
            </div>
        </div>
    </div>

    <!-- Page Boissons -->
    <div class="details-page" id="boissonsPage" style="background-image: url('https://images.unsplash.com/photo-1544145945-f90425340c7e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1920&q=80');">
        <div class="details-overlay">
            <button class="back-button" onclick="showFamilies()">
                <i class="fas fa-arrow-left"></i> Retour
            </button>
            <div class="details-container">
                <h2 class="page-title">Boissons</h2>
                <div class="items-grid">
                    <div class="item-card">
                        <div class="item-name">Nespresso</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Cappuccino</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Frappucino glacé</div>
                        <div class="item-price">2500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Thé mixte</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Thé Cherry's</div>
                        <div class="item-price">1500f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Thé malien</div>
                        <div class="item-price">1000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Ener cherry's</div>
                        <div class="item-price">2000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Virginie colada</div>
                        <div class="item-price">4000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Virginie mojito</div>
                        <div class="item-price">4000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Bora bora</div>
                        <div class="item-price">4000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">San francisco</div>
                        <div class="item-price">4000f</div>
                    </div>
                    <div class="item-card">
                        <div class="item-name">Coco lait</div>
                        <div class="item-price">5000f</div>
                    </div>
                </div>
                <a href="https://wa.me/22384124748" class="whatsapp-button" target="_blank">
                    <i class="fab fa-whatsapp"></i> Commander sur WhatsApp
                </a>
            </div>
        </div>
    </div>

    <script>
        function showFamilies() {
            document.getElementById('homePage').style.display = 'none';
            document.getElementById('familiesPage').style.display = 'block';
            window.scrollTo(0, 0);
        }

        function showHome() {
            document.getElementById('homePage').style.display = 'flex';
            document.getElementById('familiesPage').style.display = 'none';
            document.querySelectorAll('.details-page').forEach(page => {
                page.style.display = 'none';
            });
            window.scrollTo(0, 0);
        }

        function showDetails(category) {
            document.getElementById('familiesPage').style.display = 'none';
            document.querySelectorAll('.details-page').forEach(page => {
                page.style.display = 'none';
            });
            
            const pageId = category + 'Page';
            document.getElementById(pageId).style.display = 'block';
            window.scrollTo(0, 0);
        }

        // Ajouter des effets de scroll
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelectorAll('.details-page');
            const speed = 0.5;

            parallax.forEach(element => {
                const yPos = -(scrolled * speed);
                element.style.backgroundPosition = `center ${yPos}px`;
            });
        });
    </script>
</body>
</html>
