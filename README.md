```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BCF Bamboo Craft</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
background:#f8f5f2;
color:#333;
}

header{
background:#2d1b12;
color:white;
padding:15px;
display:flex;
justify-content:space-between;
align-items:center;
}

.logo{
font-size:24px;
font-weight:bold;
}

.hero{
height:400px;
background:url('https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?q=80&w=1200&auto=format&fit=crop') center/cover;
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
