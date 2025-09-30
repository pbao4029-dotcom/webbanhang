<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cửa Hàng Thời Trang Hiện Đại</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        /* --- Cài đặt chung & Biến màu được tinh chỉnh --- */
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&display=swap');

        :root {
            --primary-color: #006d77;  /* Xanh rêu đậm sang trọng */
            --secondary-color: #2b2d42; /* Xanh than (chữ chính) */
            --accent-color: #e29578; /* Màu cam đất làm điểm nhấn */
            --background-color: #fdfdfd; 
            --light-color: #fff;
            --font-family: 'Montserrat', sans-serif;
            --soft-shadow: 0 8px 25px rgba(0, 0, 0, 0.08);
            --border-radius: 12px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--background-color);
            color: var(--secondary-color);
            font-family: var(--font-family);
            line-height: 1.7;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }

        img {
            max-width: 100%;
            display: block;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* --- Header --- */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.5rem 0; /* Tăng padding */
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px); /* Hiệu ứng mờ kính */
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-color);
        }
        
        .navbar a {
            margin: 0 1.2rem;
            font-weight: 600;
            transition: color 0.3s ease;
        }
        
        .navbar a:hover {
            color: var(--primary-color);
        }

        .icons a {
            font-size: 1.2rem;
            margin-left: 1.8rem;
        }

        /* --- Hero Section --- */
        .hero {
            height: 90vh; /* Cao hơn */
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1483985988355-763728e1935b?q=80&w=2070&auto=format&fit=crop') no-repeat center center/cover;
            display: flex;
            align-items: center;
            text-align: left; /* Căn lề trái */
            color: var(--light-color);
        }

        .hero-content {
            max-width: 600px;
        }

        .hero-content h1 {
            font-size: 3.8rem;
            line-height: 1.2;
            margin-bottom: 1rem;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 2.5rem;
        }

        /* --- Nút Bấm Nâng Cấp --- */
        .btn {
            display: inline-block;
            background-color: var(--accent-color);
            color: var(--light-color);
            padding: 14px 35px;
            border-radius: 50px; /* Bo tròn hơn */
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 4px 15px rgba(226, 149, 120, 0.4);
            transition: all 0.3s ease;
        }
        
        .btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(226, 149, 120, 0.5);
        }

        /* --- Khu vực chung --- */
        .section {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.8rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }
        .section-subtitle {
            text-align: center;
            font-size: 1rem;
            color: #888;
            margin-bottom: 4rem;
        }

        /* --- KHU VỰC MỚI: Danh Mục Sản Phẩm --- */
        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }
        .category-card {
            position: relative;
            overflow: hidden;
            border-radius: var(--border-radius);
            box-shadow: var(--soft-shadow);
            height: 350px;
        }
        .category-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s ease;
        }
        .category-card:hover img {
            transform: scale(1.1);
        }
        .category-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(to top, rgba(0,0,0,0.7), rgba(0,0,0,0));
            display: flex;
            align-items: flex-end;
            padding: 2rem;
            color: white;
        }
        .category-overlay h3 {
            font-size: 1.8rem;
            font-weight: 700;
        }

        /* --- Thẻ Sản Phẩm Nâng Cấp --- */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2.5rem;
        }
        
        .product-card {
            background-color: var(--light-color);
            border-radius: var(--border-radius);
            box-shadow: var(--soft-shadow);
            text-align: left;
            overflow: hidden; /* Ẩn các phần thừa */
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.12);
        }
        
        .product-image-container {
            position: relative;
            overflow: hidden;
        }

        .product-image-container img {
            width: 100%;
            height: 320px;
            object-fit: cover;
            transition: transform 0.4s ease;
        }
        .product-card:hover .product-image-container img {
            transform: scale(1.05); /* Hiệu ứng zoom ảnh khi hover */
        }
        
        .badge {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background-color: var(--accent-color);
            color: var(--light-color);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
        }
        
        .product-hover-actions {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.9);
            padding: 1rem;
            text-align: center;
            transform: translateY(100%); /* Ẩn ban đầu */
            transition: transform 0.4s ease;
        }
        .product-card:hover .product-hover-actions {
            transform: translateY(0); /* Hiện ra khi hover card */
        }
        .product-hover-actions .btn {
            width: 100%;
            padding: 12px;
            background-color: var(--secondary-color);
            box-shadow: none;
        }
        .product-hover-actions .btn:hover {
            background-color: var(--primary-color);
            transform: translateY(0);
            box-shadow: none;
        }
        
        .product-info {
            padding: 1.5rem;
        }

        .product-info h3 {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }
        
        .product-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--primary-color);
        }
        .product-price .old-price {
            font-size: 0.9rem;
            text-decoration: line-through;
            color: #999;
            margin-left: 0.5rem;
        }

        /* Animation khi cuộn trang */
        .reveal {
            position: relative;
            transform: translateY(50px);
            opacity: 0;
            transition: all 0.8s ease;
        }
        .reveal.active {
            transform: translateY(0px);
            opacity: 1;
        }

        /* --- KHU VỰC MỚI: Newsletter --- */
        .newsletter-section {
            background-color: #eaf4f4;
            padding: 4rem 0;
            text-align: center;
        }
        .newsletter-section h2 {
            font-size: 2.2rem;
            margin-bottom: 1rem;
        }
        .newsletter-section p {
            max-width: 500px;
            margin: 0 auto 2rem;
        }
        .newsletter-form {
            display: flex;
            justify-content: center;
            max-width: 500px;
            margin: 0 auto;
        }
        .newsletter-form input {
            flex-grow: 1;
            padding: 14px 20px;
            border: 1px solid #ddd;
            border-radius: 50px 0 0 50px;
            outline: none;
            font-size: 1rem;
        }
        .newsletter-form .btn {
            border-radius: 0 50px 50px 0;
            box-shadow: none;
        }

        /* --- Footer --- */
        .footer {
            background-color: var(--secondary-color);
            color: #ccc;
            padding: 4rem 0 1.5rem;
            margin-top: 5rem;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 2rem;
            margin-bottom: 3rem;
        }
        
        .footer-column { flex: 1; min-width: 220px; }
        .footer-column h3 { margin-bottom: 1.5rem; color: var(--light-color); }
        .footer-column ul { list-style: none; }
        .footer-column ul li { margin-bottom: 0.8rem; }
        .footer-column ul a:hover { color: var(--accent-color); text-decoration: underline; }
        .social-icons a { font-size: 1.5rem; margin-right: 1rem; }
        
        .footer-bottom {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #444;
        }
    </style>
</head>
<body>
    
    <header>
        <div class="container header">
            <a href="#" class="logo">AURA</a>
            <nav class="navbar">
                <a href="#">Trang Chủ</a>
                <a href="#categories">Danh Mục</a>
                <a href="#products">Sản Phẩm</a>
                <a href="#">Liên Hệ</a>
            </nav>
            <div class="icons">
                <a href="#"><i class="fas fa-search"></i></a>
                <a href="#"><i class="fas fa-shopping-bag"></i></a>
                <a href="#"><i class="fas fa-user"></i></a>
            </div>
        </div>
    </header>

    <main>
        <section class="hero">
            <div class="container hero-content">
                <h1>Vẻ Đẹp Trong Từng Sợi Vải</h1>
                <p>Khám phá những thiết kế độc quyền, nơi phong cách và chất lượng giao thoa.</p>
                <a href="#products" class="btn">Mua Sắm Ngay</a>
            </div>
        </section>

        <section id="categories" class="section">
            <div class="container">
                <h2 class="section-title">Khám Phá Danh Mục</h2>
                <p class="section-subtitle">Tìm kiếm phong cách phù hợp với bạn</p>
                <div class="category-grid">
                    <a href="#" class="category-card reveal">
                        <img src="https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?q=80&w=1887&auto=format&fit=crop" alt="Thời trang nữ">
                        <div class="category-overlay"><h3>Thời Trang Nữ</h3></div>
                    </a>
                    <a href="#" class="category-card reveal">
                        <img src="https://images.unsplash.com/photo-1610384104075-e04c883355e5?q=80&w=1887&auto=format&fit=crop" alt="Thời trang nam">
                        <div class="category-overlay"><h3>Thời Trang Nam</h3></div>
                    </a>
                    <a href="#" class="category-card reveal">
                        <img src="https://images.unsplash.com/photo-1526857240824-a2be53970a74?q=80&w=1887&auto=format&fit=crop" alt="Phụ kiện">
                        <div class="category-overlay"><h3>Phụ Kiện</h3></div>
                    </a>
                </div>
            </div>
        </section>

        <section id="products" class="section">
            <div class="container">
                <h2 class="section-title">Hàng Mới Về</h2>
                <p class="section-subtitle">Những sản phẩm được yêu thích nhất trong tuần này</p>
                <div class="product-grid">
                    <div class="product-card reveal">
                        <div class="product-image-container">
                            <img src="https://images.unsplash.com/photo-1588117265224-d26d2e35a4ca?q=80&w=1887&auto=format&fit=crop" alt="Túi da">
                            <span class="badge">Sale</span>
                            <div class="product-hover-actions"><a href="#" class="btn">Thêm vào giỏ</a></div>
                        </div>
                        <div class="product-info">
                            <h3>Túi Xách Da Cao Cấp</h3>
                            <p class="product-price">1.890.000₫ <span class="old-price">2.500.000₫</span></p>
                        </div>
                    </div>
                    <div class="product-card reveal">
                        <div class="product-image-container">
                             <img src="https://images.unsplash.com/photo-1620799140408-edc6d5f9650d?q=80&w=1972&auto=format&fit=crop" alt="Áo hoodie">
                             <div class="product-hover-actions"><a href="#" class="btn">Thêm vào giỏ</a></div>
                        </div>
                        <div class="product-info">
                            <h3>Áo Hoodie Nỉ Bông</h3>
                            <p class="product-price">850.000₫</p>
                        </div>
                    </div>
                    <div class="product-card reveal">
                        <div class="product-image-container">
                            <img src="https://images.unsplash.com/photo-1560769629-975ec94e6a86?q=80&w=1964&auto=format&fit=crop" alt="Giày da">
                             <span class="badge">New</span>
                            <div class="product-hover-actions"><a href="#" class="btn">Thêm vào giỏ</a></div>
                        </div>
                        <div class="product-info">
                            <h3>Giày Da Cổ Điển</h3>
                            <p class="product-price">3.200.000₫</p>
                        </div>
                    </div>
                    <div class="product-card reveal">
                        <div class="product-image-container">
                             <img src="https://images.unsplash.com/photo-1572635196237-14b3f281503f?q=80&w=1780&auto=format&fit=crop" alt="Kính râm">
                            <div class="product-hover-actions"><a href="#" class="btn">Thêm vào giỏ</a></div>
                        </div>
                        <div class="product-info">
                            <h3>Kính Mát Tròn Unisex</h3>
                            <p class="product-price">1.250.000₫</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="newsletter-section">
            <div class="container reveal">
                <h2>Đăng Ký Nhận Tin</h2>
                <p>Đừng bỏ lỡ các sản phẩm mới và chương trình khuyến mãi độc quyền của chúng tôi!</p>
                <form class="newsletter-form">
                    <input type="email" placeholder="Nhập email của bạn...">
                    <button type="submit" class="btn">Đăng ký</button>
                </form>
            </div>
        </section>

    </main>
    
    <footer class="footer">
        <div class="container footer-content">
            <div class="footer-column">
                <h3 class="logo">AURA</h3>
                <p>Mang đến những sản phẩm thời trang chất lượng, bền vững và đầy phong cách.</p>
            </div>
            <div class="footer-column">
                <h3>Cửa Hàng</h3>
                <ul>
                    <li><a href="#">Thời Trang Nam</a></li>
                    <li><a href="#">Thời Trang Nữ</a></li>
                    <li><a href="#">Phụ Kiện</a></li>
                    <li><a href="#">Hàng Giảm Giá</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Hỗ Trợ</h3>
                <ul>
                    <li><a href="#">Câu Hỏi Thường Gặp</a></li>
                    <li><a href="#">Chính Sách Vận Chuyển</a></li>
                    <li><a href="#">Chính Sách Đổi Trả</a></li>
                    <li><a href="#">Liên Hệ</a></li>
                </ul>
            </div>
            <div class="footer-column">
                <h3>Theo Dõi Chúng Tôi</h3>
                <div class="social-icons">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-tiktok"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2025 AURA. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");

            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 150; // Khoảng cách để phần tử được coi là hiển thị

                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("active");
                } else {
                    reveals[i].classList.remove("active");
                }
            }
        }

        window.addEventListener("scroll", reveal);
        // Chạy lần đầu để kiểm tra các phần tử đã ở trong tầm nhìn
        reveal();
    </script>
</body>
</html>
