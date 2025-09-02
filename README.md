  <!-- ...existing code... -->
    <script>
      let currentSlide = 0;
      const slides = document.querySelectorAll('.slider-img');
      function showSlide(idx) {
        slides.forEach((img, i) => {
          img.classList.toggle('active', i === idx);
        });
      }
      function moveSlide(dir) {
        currentSlide = (currentSlide + dir + slides.length) % slides.length;
        showSlide(currentSlide);
      }
      showSlide(currentSlide);
    </script>
      .image-slider {
        background: #fff;
        border-radius: 24px;
        box-shadow: 0 2px 16px #e0e0e0;
        padding: 32px 16px;
        margin-bottom: 48px;
      }
      .slider-container {
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        max-width: 400px;
        margin: 0 auto;
      }
      .slider-images {
        width: 400px;
        height: 250px;
        overflow: hidden;
        position: relative;
      }
      .slider-img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        position: absolute;
        left: 0; top: 0;
        opacity: 0;
        transition: opacity 0.5s;
      }
      .slider-img.active {
        opacity: 1;
        position: relative;
      }
      .slider-btn {
        background: #222;
        color: #fff;
        border: none;
        border-radius: 50%;
        width: 36px;
        height: 36px;
        font-size: 1.5rem;
        cursor: pointer;
        margin: 0 8px;
        transition: background 0.2s;
      }
      .slider-btn:hover {
        background: #3498db;
      }

<!DOCTYPE html>
<html lang="ar">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Handmade Business</title>
  <link href="https://fonts.googleapis.com/css2?family=Yeseva+One&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css" />
    <style>
      body {
        margin: 0;
        font-family: 'Segoe UI', Arial, sans-serif;
        background: linear-gradient(135deg, #F0EEE6 60%, #fff 100%);
        min-height: 100vh;
        overflow-x: hidden;
      }
      .animated-bg {
        position: fixed;
        top: 0; left: 0; width: 100vw; height: 100vh;
        z-index: -1;
        background: radial-gradient(circle at 20% 20%, #e0e0e0 0%, transparent 60%),
                    radial-gradient(circle at 80% 80%, #d1cfc7 0%, transparent 60%);
        animation: bgMove 8s linear infinite alternate;
      }
      @keyframes bgMove {
        0% { background-position: 20% 20%, 80% 80%; }
        100% { background-position: 30% 30%, 70% 70%; }
      }
      .navbar {
        position: sticky;
        top: 0;
        background: #fff;
        box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 40px;
        height: 70px;
        z-index: 10;
      }
      .navbar-title {
        text-shadow: 2px 2px 8px #e0e0e0;
      }
      .navbar-links a {
        transition: background 0.2s, transform 0.2s;
      }
      .navbar-links a.active, .navbar-links a:hover {
        background: #222;
        color: #fff;
        transform: scale(1.08);
      }
      .hero {
        margin-top: 0;
        min-height: 60vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        position: relative;
        background: transparent;
      }
      .hero .hero-icon {
        background: #fff;
        box-shadow: 0 2px 8px #eee;
        border-radius: 50%;
        width: 70px;
        height: 70px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0 auto 24px auto;
        animation: iconBounce 2s infinite alternate;
      }
      @keyframes iconBounce {
        0% { transform: translateY(0); }
        100% { transform: translateY(-12px); }
      }
      .hero h1 {
        font-size: 2.8rem;
        color: #222;
        margin-bottom: 18px;
        font-weight: 700;
        font-family: 'Yeseva One', cursive;
        text-shadow: 2px 2px 8px #e0e0e0;
        animation: fadeIn 1.2s;
      }
      .hero p {
        font-size: 1.2rem;
        color: #333;
        margin-bottom: 32px;
        animation: fadeIn 1.8s;
      }
      .hero .hero-btn {
        padding: 14px 38px;
        font-size: 1.1rem;
        border-radius: 24px;
        background: linear-gradient(90deg, #ff5e62 0%, #ff9966 100%);
        color: #fff;
        border: none;
        font-weight: 600;
        box-shadow: 0 2px 16px #eee;
        cursor: pointer;
        transition: background 0.2s, transform 0.2s;
        animation: fadeIn 2.2s;
      }
      .hero .hero-btn:hover {
        background: linear-gradient(90deg, #ff9966 0%, #ff5e62 100%);
        transform: scale(1.08);
        box-shadow: 0 4px 24px #ff996644;
      }
      @keyframes fadeIn {
        from { opacity: 0; transform: translateY(30px); }
        to { opacity: 1; transform: translateY(0); }
      }
      .wave {
        position: relative;
        width: 100vw;
        height: 60px;
        margin-top: -30px;
        z-index: 2;
      }
      .about, .products, #contact {
        box-shadow: 0 2px 16px #e0e0e0;
        border-radius: 24px;
        background: #fff;
        margin-bottom: 48px;
        padding: 32px 16px;
        animation: fadeIn 2.5s;
      }
      .navbar {
        background: #fff;
        box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 0 40px;
        height: 70px;
      }
      .navbar-logo {
        display: flex;
        align-items: center;
        gap: 12px;
      }
      .navbar-logo img {
        height: 48px;
        width: auto;
        display: block;
      }
      .navbar-title {
        font-size: 1.3rem;
        font-weight: bold;
        color: #222;
        font-family: 'Yeseva One', cursive;
      }
      .navbar-links {
        display: flex;
        align-items: center;
        gap: 32px;
      }
      .navbar-links a {
        text-decoration: none;
        color: #222;
        font-size: 1.1rem;
        font-weight: 500;
        padding: 8px 18px;
        border-radius: 8px;
        transition: background 0.2s;
      }
      .navbar-links a.active, .navbar-links a:hover {
        background: #222;
        color: #fff;
      }
      .hero {
        margin-top: 0;
        min-height: 60vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        text-align: center;
        position: relative;
        background: #F0EEE6;
      }
      .hero .hero-icon {
        background: #fff;
        box-shadow: 0 2px 8px #eee;
        border-radius: 50%;
        width: 70px;
        height: 70px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0 auto 24px auto;
      }
      .hero .hero-icon img {
        width: 40px;
        height: 40px;
      }
      .hero h1 {
        font-size: 2.8rem;
        color: #222;
        margin-bottom: 18px;
        font-weight: 700;
        font-family: 'Yeseva One', cursive;
      }
      .hero p {
        font-size: 1.2rem;
        color: #333;
        margin-bottom: 32px;
      }
      .hero .hero-btn {
        padding: 14px 38px;
        font-size: 1.1rem;
        border-radius: 24px;
        background: linear-gradient(90deg, #ff5e62 0%, #ff9966 100%);
        color: #fff;
        border: none;
        font-weight: 600;
        box-shadow: 0 2px 8px #eee;
        cursor: pointer;
        transition: background 0.2s;
      }
      .hero .hero-btn:hover {
        background: linear-gradient(90deg, #ff9966 0%, #ff5e62 100%);
      }
      .hero {
        margin-top: 48px;
        text-align: center;
      }
      .hero h1 {
  font-size: 2.5rem;
  color: #222;
  margin-bottom: 16px;
  font-weight: 700;
  font-family: 'Yeseva One', cursive;
      }
    </style>
  </head>
  <body>
    <nav class="navbar">
      <div class="navbar-logo">
        <span class="navbar-title">Baladi Sooq</span>
      </div>
      <div class="navbar-links">
        <a href="#" class="active">الرئيسية</a>
        <a href="#art">فن</a>
        <a href="#food">طعام</a>
        <a href="#handmade">أعمال يدوية</a>
        <a href="#paintings">لوحات</a>
        <a href="#contact">تواصل معنا</a>
      </div>
    </nav>
    <section class="hero">
      <div class="hero-icon">
        <img src="../Downloads/photo_5886544857659459721_x.jpg" alt="Baladi Sooq Logo" style="width:56px;height:56px;border-radius:16px;object-fit:cover;">
      </div>
      <h1>Baladi Sooq - سوق إلكتروني شامل</h1>
      <p>منصة تجمع أفضل المتاجر الإلكترونية في مجالات الفن، الطعام، الأعمال اليدوية، اللوحات وغيرها. اختر القسم الذي يناسبك واكتشف المتاجر المميزة!</p>
      <button class="hero-btn">تصفح الأقسام</button>
    </section>
    <!-- معرض الصور يمكن إضافته لاحقاً لكل قسم -->
    <section id="art" style="max-width:900px;margin:48px auto 0 auto;">
      <h2 style="text-align:center;color:#222;font-family:'Yeseva One',cursive;">فن</h2>
      <div style="display:flex;flex-wrap:wrap;gap:24px;justify-content:center;margin-top:24px;">
        <!-- أضف متاجر الفن هنا -->
        <div style="background:#fff;border-radius:16px;box-shadow:0 2px 8px #eee;padding:16px;width:220px;">
          <img src="https://via.placeholder.com/200x150?text=متجر+فن" alt="متجر فن" style="width:100%;border-radius:12px;">
          <h3 style="color:#222;margin:12px 0 8px 0;font-family:'Yeseva One',cursive;">متجر فن 1</h3>
          <a href="#" style="color:#3498db;">زيارة المتجر</a>
        </div>
      </div>
    </section>
    <section id="food" style="max-width:900px;margin:48px auto 0 auto;">
      <h2 style="text-align:center;color:#222;font-family:'Yeseva One',cursive;">طعام</h2>
      <div style="display:flex;flex-wrap:wrap;gap:24px;justify-content:center;margin-top:24px;">
        <!-- أضف متاجر الطعام هنا -->
        <div style="background:#fff;border-radius:16px;box-shadow:0 2px 8px #eee;padding:16px;width:220px;">
          <img src="https://via.placeholder.com/200x150?text=متجر+طعام" alt="متجر طعام" style="width:100%;border-radius:12px;">
          <h3 style="color:#222;margin:12px 0 8px 0;font-family:'Yeseva One',cursive;">متجر طعام 1</h3>
          <a href="#" style="color:#3498db;">زيارة المتجر</a>
        </div>
      </div>
    </section>
    <section id="handmade" style="max-width:900px;margin:48px auto 0 auto;">
      <h2 style="text-align:center;color:#222;font-family:'Yeseva One',cursive;">أعمال يدوية</h2>
      <div style="display:flex;flex-wrap:wrap;gap:24px;justify-content:center;margin-top:24px;">
        <!-- أضف متاجر الأعمال اليدوية هنا -->
        <div style="background:#fff;border-radius:16px;box-shadow:0 2px 8px #eee;padding:16px;width:220px;">
          <img src="https://via.placeholder.com/200x150?text=متجر+يدوي" alt="متجر يدوي" style="width:100%;border-radius:12px;">
          <h3 style="color:#222;margin:12px 0 8px 0;font-family:'Yeseva One',cursive;">متجر يدوي 1</h3>
          <a href="#" style="color:#3498db;">زيارة المتجر</a>
        </div>
      </div>
    </section>
    <section id="paintings" style="max-width:900px;margin:48px auto 0 auto;">
      <h2 style="text-align:center;color:#222;font-family:'Yeseva One',cursive;">لوحات</h2>
      <div style="display:flex;flex-wrap:wrap;gap:24px;justify-content:center;margin-top:24px;">
        <!-- أضف متاجر اللوحات هنا -->
        <div style="background:#fff;border-radius:16px;box-shadow:0 2px 8px #eee;padding:16px;width:220px;">
          <img src="https://via.placeholder.com/200x150?text=متجر+لوحات" alt="متجر لوحات" style="width:100%;border-radius:12px;">
          <h3 style="color:#222;margin:12px 0 8px 0;font-family:'Yeseva One',cursive;">متجر لوحات 1</h3>
          <a href="#" style="color:#3498db;">زيارة المتجر</a>
        </div>
      </div>
    </section>
    <section id="contact" style="max-width:700px;margin:48px auto 32px auto;text-align:center;">
      <h2 style="color:#3498db;">تواصل معنا</h2>
      <p style="color:#333;">للاستفسار أو التعاون، راسلنا عبر البريد الإلكتروني: <a href="mailto:info@baladi.com" style="color:#3498db;">info@baladi.com</a></p>
      <div style="margin-top:16px;">
  <a href="tel:+123456789" style="margin:0 8px;color:#222;font-size:1.8rem;" title="اتصل بنا"><i class="fas fa-phone"></i></a>
  <a href="mailto:info@baladi.com" style="margin:0 8px;color:#222;font-size:1.8rem;" title="راسلنا"><i class="fas fa-envelope"></i></a>
  <a href="https://instagram.com" target="_blank" style="margin:0 8px;color:#222;font-size:1.8rem;" title="انستغرام"><i class="fab fa-instagram"></i></a>
      </div>
    </section>
  </body>
</html>
