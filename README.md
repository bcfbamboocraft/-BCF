<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SnapShop - Online Shopping India</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f1f3f6;
        }

        /* Top Bar */
        .top-bar {
            background: linear-gradient(135deg, #e40046 0%, #c2185b 100%);
            color: white;
            padding: 8px 15px;
            font-size: 12px;
            text-align: center;
        }

        /* Header */
        .header {
            background: #e40046;
            padding: 10px 15px;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-top {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 10px;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            color: white;
            text-decoration: none;
        }

        .logo span {
            color: #ffeb3b;
        }

        .search-bar {
            flex: 1;
            display: flex;
            background: white;
            border-radius: 4px;
            overflow: hidden;
        }

        .search-bar input {
            flex: 1;
            padding: 10px 12px;
            border: none;
            outline: none;
            font-size: 14px;
        }

        .search-bar button {
            background: #ffeb3b;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
        }

        .search-bar button svg {
            width: 20px;
            height: 20px;
        }

        .header-icons {
            display: flex;
            gap: 15px;
        }

        .header-icon {
            color: white;
            text-decoration: none;
            font-size: 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .header-icon svg {
            width: 24px;
            height: 24px;
            margin-bottom: 2px;
        }

        /* Categories Nav */
        .categories-nav {
            background: white;
            padding: 10px;
            overflow-x: auto;
            white-space: nowrap;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .categories-nav::-webkit-scrollbar {
            display: none;
        }

        .cat-item {
            display: inline-block;
            text-align: center;
            padding: 5px 12px;
            text-decoration: none;
            color: #333;
            font-size: 12px;
        }

        .cat-item img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 5px;
            background: #f5f5f5;
        }

        .cat-item span {
            display: block;
        }

        /* Banner Slider */
        .banner-section {
            padding: 10px;
        }

        .banner-slider {
            position: relative;
            overflow: hidden;
            border-radius: 8px;
        }

        .banner-slide {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 30px 20px;
            color: white;
            text-align: center;
            min-height: 150px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .banner-slide h2 {
            font-size: 22px;
            margin-bottom: 8px;
        }

        .banner-slide p {
            font-size: 14px;
            opacity: 0.9;
        }

        .banner-dots {
            display: flex;
            justify-content: center;
            gap: 6px;
            margin-top: 10px;
        }

        .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: #ccc;
        }

        .dot.active {
            background: #e40046;
        }

        /* Offer Strip */
        .offer-strip {
            display: flex;
            gap: 10px;
            padding: 10px;
            overflow-x: auto;
        }

        .offer-strip::-webkit-scrollbar {
            display: none;
        }

        .offer-card {
            flex-shrink: 0;
            background: white;
            border-radius: 8px;
            padding: 15px;
            text-align: center;
            min-width: 100px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }

        .offer-card .icon {
            font-size: 28px;
            margin-bottom: 5px;
        }

        .offer-card .title {
            font-size: 11px;
            color: #333;
            font-weight: 600;
        }

        .offer-card .discount {
            font-size: 10px;
            color: #e40046;
            margin-top: 3px;
        }

        /* Section */
        .section {
            background: white;
            margin: 10px;
            border-radius: 8px;
            padding: 15px;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .section-title {
            font-size: 16px;
            font-weight: 600;
            color: #333;
        }

        .view-all {
            color: #e40046;
            text-decoration: none;
            font-size: 13px;
        }

        /* Product Grid */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
        }

        .product-card {
            background: #fafafa;
            border-radius: 8px;
            padding: 10px;
            text-decoration: none;
            color: inherit;
        }

        .product-image {
            width: 100%;
            aspect-ratio: 1;
            object-fit: contain;
            background: white;
            border-radius: 6px;
            margin-bottom: 10px;
        }

        .product-name {
            font-size: 13px;
            color: #333;
            margin-bottom: 5px;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-price {
            display: flex;
            align-items: center;
            gap: 6px;
            flex-wrap: wrap;
        }

        .current-price {
            font-size: 15px;
            font-weight: 600;
            color: #333;
        }

        .original-price {
            font-size: 12px;
            color: #888;
            text-decoration: line-through;
        }

        .discount-badge {
            font-size: 11px;
            color: #388e3c;
            font-weight: 600;
        }

        .rating {
            display: flex;
            align-items: center;
            gap: 4px;
            margin-top: 5px;
        }

        .rating-badge {
            background: #388e3c;
            color: white;
            padding: 2px 6px;
            border-radius: 3px;
            font-size: 11px;
            display: flex;
            align-items: center;
            gap: 2px;
        }

        .rating-count {
            font-size: 11px;
            color: #888;
        }

        /* Deal Timer */
        .deal-timer {
            background: linear-gradient(135deg, #ff6b6b 0%, #e40046 100%);
            color: white;
            padding: 15px;
            margin: 10px;
            border-radius: 8px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .deal-timer-left h3 {
            font-size: 18px;
            margin-bottom: 5px;
        }

        .deal-timer-left p {
            font-size: 12px;
            opacity: 0.9;
        }

        .timer {
            display: flex;
            gap: 5px;
        }

        .timer-box {
            background: rgba(255,255,255,0.2);
            padding: 8px 10px;
            border-radius: 5px;
            text-align: center;
        }

        .timer-box .num {
            font-size: 18px;
            font-weight: bold;
        }

        .timer-box .label {
            font-size: 9px;
            opacity: 0.8;
        }

        /* Brand Section */
        .brand-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .brand-item {
            background: #f9f9f9;
            border-radius: 8px;
            padding: 15px 10px;
            text-align: center;
        }

        .brand-item img {
            width: 50px;
            height: 50px;
            object-fit: contain;
            margin-bottom: 5px;
        }

        .brand-item span {
            font-size: 10px;
            color: #666;
        }

        /* Footer Nav */
        .footer-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: white;
            display: flex;
            justify-content: space-around;
            padding: 8px 0;
            box-shadow: 0 -2px 10px rgba(0,0,0,0.1);
            z-index: 100;
        }

        .footer-nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-decoration: none;
            color: #666;
            font-size: 11px;
        }

        .footer-nav-item.active {
            color: #e40046;
        }

        .footer-nav-item svg {
            width: 24px;
            height: 24px;
            margin-bottom: 3px;
        }

        /* Bottom Spacing */
        .bottom-space {
            height: 70px;
        }

        /* App Download Banner */
        .app-banner {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            margin: 10px;
            border-radius: 8px;
            padding: 20px;
            color: white;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .app-banner-text h3 {
            font-size: 16px;
            margin-bottom: 5px;
        }

        .app-banner-text p {
            font-size: 12px;
            opacity: 0.8;
            margin-bottom: 10px;
        }

        .app-btn {
            background: #e40046;
            color: white;
            padding: 8px 20px;
            border-radius: 5px;
            text-decoration: none;
            font-size: 13px;
            display: inline-block;
        }

        /* Recently Viewed */
        .horizontal-scroll {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 5px;
        }

        .horizontal-scroll::-webkit-scrollbar {
            display: none;
        }

        .horizontal-card {
            flex-shrink: 0;
            width: 130px;
            background: #fafafa;
            border-radius: 8px;
            padding: 10px;
            text-align: center;
        }

        .horizontal-card img {
            width: 80px;
            height: 80px;
            object-fit: contain;
            margin-bottom: 8px;
        }

        .horizontal-card .name {
            font-size: 12px;
            color: #333;
            margin-bottom: 5px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .horizontal-card .price {
            font-size: 13px;
            font-weight: 600;
            color: #e40046;
        }
    </style>
</head>
<body>

    <!-- Top Offer Bar -->
    <div class="top-bar">
        🎉 अतिरिक्त 10% छूट | कोड: SNAP10 | आज ही ऑर्डर करें!
    </div>

    <!-- Header -->
    <header class="header">
        <div class="header-top">
            <a href="#" class="logo">Snap<span>Shop</span></a>
            <div class="search-bar">
                <input type="text" placeholder="प्रोडक्ट खोजें...">
                <button>
                    <svg fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"/>
                    </svg>
                </button>
            </div>
        </div>
    </header>

    <!-- Categories Navigation -->
    <nav class="categories-nav">
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/FF6B6B/fff?text=📱)" alt="Mobile">
            <span>मोबाइल</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/4ECDC4/fff?text=👗)" alt="Fashion">
            <span>फैशन</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/45B7D1/fff?text=🏠)" alt="Home">
            <span>होम</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/96CEB4/fff?text=💻)" alt="Electronics">
            <span>इलेक्ट्रॉनिक्स</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/FFEAA7/fff?text=👶)" alt="Kids">
            <span>किड्स</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/DDA0DD/fff?text=💄)" alt="Beauty">
            <span>ब्यूटी</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/98D8C8/fff?text=🏃)" alt="Sports">
            <span>स्पोर्ट्स</span>
        </a>
        <a href="#" class="cat-item">
            <img src="[via.placeholder.com](https://via.placeholder.com/40/F7DC6F/fff?text=📚)" alt="Books">
            <span>किताबें</span>
        </a>
    </nav>

    <!-- Banner Slider -->
    <div class="banner-section">
        <div class="banner-slider">
            <div class="banner-slide">
                <h2>🔥 महा सेल लाइव!</h2>
                <p>70% तक की छूट सभी प्रोडक्ट्स पर</p>
            </div>
        </div>
        <div class="banner-dots">
            <span class="dot active"></span>
            <span class="dot"></span>
            <span class="dot"></span>
        </div>
    </div>

    <!-- Offer Cards -->
    <div class="offer-strip">
        <div class="offer-card">
            <div class="icon">📱</div>
            <div class="title">मोबाइल</div>
            <div class="discount">40% तक छूट</div>
        </div>
        <div class="offer-card">
            <div class="icon">👔</div>
            <div class="title">मेन्स वियर</div>
            <div class="discount">60% तक छूट</div>
        </div>
        <div class="offer-card">
            <div class="icon">👗</div>
            <div class="title">वीमेन्स</div>
            <div class="discount">70% तक छूट</div>
        </div>
        <div class="offer-card">
            <div class="icon">🏠</div>
            <div class="title">होम डेकोर</div>
            <div class="discount">50% तक छूट</div>
        </div>
        <div class="offer-card">
            <div class="icon">👟</div>
            <div class="title">फुटवियर</div>
            <div class="discount">55% तक छूट</div>
        </div>
    </div>

    <!-- Deal Timer -->
    <div class="deal-timer">
        <div class="deal-timer-left">
            <h3>⚡ फ्लैश डील</h3>
            <p>जल्दी करें, ऑफर सीमित समय के लिए!</p>
        </div>
        <div class="timer">
            <div class="timer-box">
                <div class="num">02</div>
                <div class="label">घंटे</div>
            </div>
            <div class="timer-box">
                <div class="num">45</div>
                <div class="label">मिनट</div>
            </div>
            <div class="timer-box">
                <div class="num">30</div>
                <div class="label">सेकंड</div>
            </div>
        </div>
    </div>

    <!-- Trending Products -->
    <div class="section">
        <div class="section-header">
            <h2 class="section-title">🔥 ट्रेंडिंग प्रोडक्ट्स</h2>
            <a href="#" class="view-all">सभी देखें →</a>
        </div>
        <div class="product-grid">
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Smartphone)" alt="Product" class="product-image">
                <h3 class="product-name">Realme Narzo 60 5G (8GB RAM, 128GB)</h3>
                <div class="product-price">
                    <span class="current-price">₹14,999</span>
                    <span class="original-price">₹19,999</span>
                    <span class="discount-badge">25% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.3 ★</span>
                    <span class="rating-count">(2,341)</span>
                </div>
            </a>
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Headphones)" alt="Product" class="product-image">
                <h3 class="product-name">boAt Rockerz 450 Wireless Headphones</h3>
                <div class="product-price">
                    <span class="current-price">₹1,299</span>
                    <span class="original-price">₹2,990</span>
                    <span class="discount-badge">57% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.1 ★</span>
                    <span class="rating-count">(8,920)</span>
                </div>
            </a>
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Watch)" alt="Product" class="product-image">
                <h3 class="product-name">Fire-Boltt Phoenix Smart Watch AMOLED</h3>
                <div class="product-price">
                    <span class="current-price">₹1,499</span>
                    <span class="original-price">₹8,999</span>
                    <span class="discount-badge">83% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.0 ★</span>
                    <span class="rating-count">(5,672)</span>
                </div>
            </a>
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Shoes)" alt="Product" class="product-image">
                <h3 class="product-name">Campus Running Sports Shoes for Men</h3>
                <div class="product-price">
                    <span class="current-price">₹699</span>
                    <span class="original-price">₹1,499</span>
                    <span class="discount-badge">53% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.2 ★</span>
                    <span class="rating-count">(3,445)</span>
                </div>
            </a>
        </div>
    </div>

    <!-- Top Brands -->
    <div class="section">
        <div class="section-header">
            <h2 class="section-title">🏷️ टॉप ब्रांड्स</h2>
            <a href="#" class="view-all">सभी देखें →</a>
        </div>
        <div class="brand-grid">
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/e40046?text=S)" alt="Samsung">
                <span>Samsung</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/ff6600?text=X)" alt="Xiaomi">
                <span>Xiaomi</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/000?text=N)" alt="Nike">
                <span>Nike</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/e40046?text=B)" alt="boAt">
                <span>boAt</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/003399?text=P)" alt="Puma">
                <span>Puma</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/ff0000?text=R)" alt="Realme">
                <span>Realme</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/0066cc?text=P)" alt="Philips">
                <span>Philips</span>
            </div>
            <div class="brand-item">
                <img src="[via.placeholder.com](https://via.placeholder.com/50/fff/ff69b4?text=L)" alt="Lakme">
                <span>Lakme</span>
            </div>
        </div>
    </div>

    <!-- Recently Viewed -->
    <div class="section">
        <div class="section-header">
            <h2 class="section-title">👀 हाल ही में देखे गए</h2>
        </div>
        <div class="horizontal-scroll">
            <div class="horizontal-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/80/f5f5f5/333?text=Bag)" alt="Product">
                <div class="name">Laptop Bag</div>
                <div class="price">₹599</div>
            </div>
            <div class="horizontal-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/80/f5f5f5/333?text=Shirt)" alt="Product">
                <div class="name">Casual Shirt</div>
                <div class="price">₹449</div>
            </div>
            <div class="horizontal-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/80/f5f5f5/333?text=Speaker)" alt="Product">
                <div class="name">BT Speaker</div>
                <div class="price">₹899</div>
            </div>
            <div class="horizontal-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/80/f5f5f5/333?text=Charger)" alt="Product">
                <div class="name">Fast Charger</div>
                <div class="price">₹299</div>
            </div>
            <div class="horizontal-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/80/f5f5f5/333?text=Cover)" alt="Product">
                <div class="name">Phone Cover</div>
                <div class="price">₹149</div>
            </div>
        </div>
    </div>

    <!-- App Download Banner -->
    <div class="app-banner">
        <div class="app-banner-text">
            <h3>📲 ऐप डाउनलोड करें</h3>
            <p>ऐप पर एक्सक्लूसिव ऑफर्स पाएं!</p>
            <a href="#" class="app-btn">अभी डाउनलोड करें</a>
        </div>
    </div>

    <!-- More Products -->
    <div class="section">
        <div class="section-header">
            <h2 class="section-title">💎 आपके लिए स्पेशल</h2>
            <a href="#" class="view-all">सभी देखें →</a>
        </div>
        <div class="product-grid">
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Kurta)" alt="Product" class="product-image">
                <h3 class="product-name">Men's Cotton Kurta Pajama Set Festival</h3>
                <div class="product-price">
                    <span class="current-price">₹599</span>
                    <span class="original-price">₹1,999</span>
                    <span class="discount-badge">70% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.4 ★</span>
                    <span class="rating-count">(1,234)</span>
                </div>
            </a>
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Saree)" alt="Product" class="product-image">
                <h3 class="product-name">Women's Banarasi Silk Saree with Blouse</h3>
                <div class="product-price">
                    <span class="current-price">₹899</span>
                    <span class="original-price">₹2,999</span>
                    <span class="discount-badge">70% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.5 ★</span>
                    <span class="rating-count">(4,567)</span>
                </div>
            </a>
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Mixer)" alt="Product" class="product-image">
                <h3 class="product-name">Prestige Mixer Grinder 750W 3 Jars</h3>
                <div class="product-price">
                    <span class="current-price">₹2,299</span>
                    <span class="original-price">₹4,500</span>
                    <span class="discount-badge">49% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.3 ★</span>
                    <span class="rating-count">(892)</span>
                </div>
            </a>
            <a href="#" class="product-card">
                <img src="[via.placeholder.com](https://via.placeholder.com/150/f5f5f5/333?text=Bedsheet)" alt="Product" class="product-image">
                <h3 class="product-name">Double Bedsheet with 2 Pillow Covers</h3>
                <div class="product-price">
                    <span class="current-price">₹349</span>
                    <span class="original-price">₹999</span>
                    <span class="discount-badge">65% छूट</span>
                </div>
                <div class="rating">
                    <span class="rating-badge">4.1 ★</span>
                    <span class="rating-count">(6,789)</span>
                </div>
            </a>
        </div>
    </div>

    <!-- Bottom Space for Footer Nav -->
    <div class="bottom-space"></div>

    <!-- Footer Navigation -->
    <nav class="footer-nav">
        <a href="#" class="footer-nav-item active">
            <svg fill="currentColor" viewBox="0 0 24 24">
                <path d="M10 20v-6h4v6h5v-8h3L12 3 2 12h3v8z"/>
            </svg>
            <span>होम</span>
        </a>
        <a href="#" class="footer-nav-item">
            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
            </svg>
            <span>कैटेगरी</span>
        </a>
        <a href="#" class="footer-nav-item">
            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"/>
            </svg>
            <span>कार्ट</span>
        </a>
        <a href="#" class="footer-nav-item">
            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"/>
            </svg>
            <span>विशलिस्ट</span>
        </a>
        <a href="#" class="footer-nav-item">
            <svg fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"/>
            </svg>
            <span>अकाउंट</span>
        </a>
    </nav>

</body>
</html>
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
color:white;
padding:20px;
}

.hero h1{
font-size:38px;
background:rgba(0,0,0,0.5);
padding:10px 20px;
border-radius:10px;
margin-bottom:10px;
}

.hero p{
background:rgba(0,0,0,0.5);
padding:10px;
border-radius:10px;
margin-bottom:20px;
}

.btn{
background:#b77b45;
color:white;
padding:12px 25px;
text-decoration:none;
border-radius:8px;
font-weight:bold;
display:inline-block;
}

.section{
padding:50px 20px;
text-align:center;
}

.section h2{
font-size:30px;
margin-bottom:30px;
color:#2d1b12;
}

.products{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:20px;
}

.card{
background:white;
padding:15px;
border-radius:12px;
box-shadow:0 2px 10px rgba(0,0,0,0.1);
}

.card img{
width:100%;
height:220px;
object-fit:cover;
border-radius:10px;
}

.card h3{
margin:15px 0 10px;
}

.price{
color:green;
font-weight:bold;
margin-bottom:10px;
}

.features{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
gap:20px;
}

.feature-box{
background:white;
padding:20px;
border-radius:12px;
box-shadow:0 2px 8px rgba(0,0,0,0.1);
}

footer{
background:#2d1b12;
color:white;
text-align:center;
padding:20px;
margin-top:40px;
}

.whatsapp{
position:fixed;
bottom:20px;
right:20px;
background:#25D366;
color:white;
padding:15px 20px;
border-radius:50px;
text-decoration:none;
font-weight:bold;
}

</style>
</head>

<body>

<header>
<div class="logo">BCF Bamboo Craft</div>
<div>Handmade Premium Products</div>
</header>

<section class="hero">
<h1>Premium Bamboo Craft Collection</h1>
<p>Eco-Friendly Handmade Furniture & Decor</p>
<a href="#products" class="btn">Shop Now</a>
</section>

<section class="section" id="products">

<h2>Featured Products</h2>

<div class="products">

<div class="card">
<img src="https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?q=80&w=800&auto=format&fit=crop">
<h3>Bamboo Chair</h3>
<div class="price">₹1599</div>
<a href="https://wa.me/916397206899" class="btn">Order Now</a>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1517705008128-361805f42e86?q=80&w=800&auto=format&fit=crop">
<h3>Foldable Bed</h3>
<div class="price">₹1299</div>
<a href="https://wa.me/916397206899" class="btn">Order Now</a>
</div>

<div class="card">
<img src="https://images.unsplash.com/photo-1519710164239-da123dc03ef4?q=80&w=800&auto=format&fit=crop">
<h3>Handmade Basket</h3>
<div class="price">₹399</div>
<a href="https://wa.me/916397206899" class="btn">Order Now</a>
</div>

</div>

</section>

<section class="section">

<h2>Why Choose Us?</h2>

<div class="features">

<div class="feature-box">
✅ Handmade Products
</div>

<div class="feature-box">
🌿 Eco-Friendly Material
</div>

<div class="feature-box">
🚚 Fast Delivery
</div>

<div class="feature-box">
💯 Premium Quality
</div>

</div>

</section>

<footer>

<h3>BCF Bamboo Craft</h3>

<p>Bareilly, Uttar Pradesh</p>

<p>📞 +91 6397206899</p>

</footer>

<a class="whatsapp" href="https://wa.me/916397206899">
WhatsApp
</a>

</body>
</html>
```
