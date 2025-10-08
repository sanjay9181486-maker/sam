<!doctype html>
<html lang="en">
<head>
  <!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-VWZXG14H76"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-VWZXG14H76');
</script>
  <!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-MVNV5S2H');</script>
<!-- End Google Tag Manager -->
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Four-Part Shopping Site</title>
  <style>
    :root{
      --accent:#2563eb;
      --muted:#6b7280;
      --bg:#f8fafc;
      --card:#ffffff;
      --glass: rgba(255,255,255,0.6);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{margin:0;background:var(--bg);color:#0f172a}
    <!-- Google Tag Manager (noscript) -->
<noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-MVNV5S2H"
height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
<!-- End Google Tag Manager (noscript) -->

    /* Layout: 4 main parts (Header, Sidebar, Main, Right panel / Cart) */
    .app{display:grid;grid-template-columns:240px 1fr 360px;grid-template-rows:72px 1fr 80px;gap:20px;min-height:100vh;padding:20px}
    header{grid-column:1/4;display:flex;align-items:center;justify-content:space-between;background:linear-gradient(90deg,var(--card),var(--glass));backdrop-filter:blur(6px);padding:12px 20px;border-radius:12px;box-shadow:0 6px 20px rgba(2,6,23,0.07)}
    header .brand{display:flex;gap:12px;align-items:center}
    .logo{width:44px;height:44px;border-radius:10px;background:conic-gradient(from 200deg at 50% 50%, #60a5fa, #7c3aed, #06b6d4);display:flex;align-items:center;justify-content:center;color:white;font-weight:700}
    .search{flex:1;margin:0 20px}
    .search input{width:100%;padding:10px 14px;border-radius:10px;border:1px solid #e6edf3}

    /* Left: Categories (Part 1) */
    .sidebar{background:var(--card);padding:18px;border-radius:12px;box-shadow:0 6px 20px rgba(2,6,23,0.03)}
    .sidebar h3{margin:0 0 12px 0}
    .cats{display:flex;flex-direction:column;gap:8px}
    .cat{padding:10px;border-radius:8px;cursor:pointer;border:1px solid transparent}
    .cat:hover{background:#f1f5f9}

    /* Main: Product grid (Part 2) */
    main{background:transparent;padding:0 0 0 0}
    .products{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:16px}
    .card{background:var(--card);padding:14px;border-radius:10px;box-shadow:0 6px 18px rgba(2,6,23,0.04);display:flex;flex-direction:column}
    .thumb{height:140px;border-radius:8px;background:linear-gradient(180deg,#eef2ff,#fff);
      display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--muted)}
    .title{font-weight:600;margin:10px 0 6px}
    .price{font-weight:700}
    .meta{display:flex;justify-content:space-between;align-items:center;margin-top:auto}
    .btn{background:var(--accent);color:white;padding:8px 12px;border-radius:8px;border:none;cursor:pointer}

    /* Right: Cart & Filters (Part 3) */
    .cart{background:var(--card);padding:16px;border-radius:12px;box-shadow:0 6px 20px rgba(2,6,23,0.03);display:flex;flex-direction:column}
    .cart h3{margin:0 0 12px}
    .cart-list{display:flex;flex-direction:column;gap:8px;max-height:400px;overflow:auto;padding-right:6px}
    .cart-item{display:flex;gap:10px;align-items:center}
    .cart-item .q{font-size:13px;color:var(--muted)}
    .checkout{margin-top:auto}

    /* Footer: Four-part fourth section (Part 4) - large info strip */
    footer{grid-column:1/4;background:linear-gradient(90deg,#0ea5a9,#7c3aed);color:white;border-radius:12px;padding:16px;display:flex;justify-content:space-between;align-items:center}
    footer .links{display:flex;gap:16px}

    /* Responsive */
    @media (max-width:980px){
      .app{grid-template-columns:1fr;grid-template-rows:72px auto auto 80px}
      header{grid-column:1/2}
      footer{grid-column:1/2;margin-top:8px}
      .cart{order:3}
    }
  </style>
</head>
<body>
  <div class="app">
    <header>
      <div class="brand">
        <div class="logo">S</div>
        <div>
          <div style="font-weight:700">ShopFour</div>
          <div style="font-size:12px;color:var(--muted)">A simple 4-part shopping template</div>
        </div>
      </div>
      <div class="search">
        <input id="searchBox" placeholder="Search products, e.g. headphones" />
      </div>
      <div style="display:flex;gap:12px;align-items:center">
        <div style="font-size:13px;color:var(--muted)">Welcome, Guest</div>
        <button class="btn" onclick="toggleCart()">Cart (<span id="cartCount">0</span>)</button>
      </div>
    </header>

    <!-- PART 1: Left sidebar categories -->
    <aside class="sidebar" aria-label="categories">
      <h3>Categories</h3>
      <div class="cats" id="categories">
        <div class="cat" onclick="filterCategory('All')">All</div>
        <div class="cat" onclick="filterCategory('Electronics')">Electronics</div>
        <div class="cat" onclick="filterCategory('Clothing')">Clothing</div>
        <div class="cat" onclick="filterCategory('Home')">Home & Kitchen</div>
        <div class="cat" onclick="filterCategory('Toys')">Toys & Games</div>
      </div>
    </aside>

    <!-- PART 2: Main product grid -->
    <main>
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:12px">
        <h2 style="margin:0">Products</h2>
        <div style="font-size:13px;color:var(--muted)">Showing <span id="productCount">0</span> products</div>
      </div>
      <div class="products" id="productGrid"></div>
    </main>

    <!-- PART 3: Cart / Filters -->
    <aside class="cart" id="cartPanel">
      <h3>Your Cart</h3>
      <div class="cart-list" id="cartList">
        <div style="color:var(--muted)">Cart is empty — add something!</div>
      </div>
      <div class="checkout">
        <div style="display:flex;justify-content:space-between;align-items:center;margin-top:12px">
          <div>
            <div style="font-size:12px;color:var(--muted)">Total</div>
            <div style="font-weight:800;font-size:18px" id="cartTotal">₹0</div>
          </div>
          <div>
            <button class="btn" onclick="checkout()">Checkout</button>
          </div>
        </div>
      </div>
    </aside>

    <!-- PART 4: Footer / Info strip -->
    <footer>
      <div>
        <div style="font-weight:800">ShopFour — Fast & Simple</div>
        <div style="font-size:13px;opacity:0.9">Free shipping on orders over ₹999</div>
      </div>
      <div class="links">
        <div style="font-size:14px">Help</div>
        <div style="font-size:14px">About</div>
        <div style="font-size:14px">Contact</div>
      </div>
    </footer>
  </div>

  <script>
    // Demo data
    const products = [
      {id:1,title:'Wireless Headphones',cat:'Electronics',price:1799},
      {id:2,title:'Smart Watch',cat:'Electronics',price:2299},
      {id:3,title:'Cotton Shirt',cat:'Clothing',price:799},
      {id:4,title:'Ceramic Mug',cat:'Home',price:249},
      {id:5,title:'Building Blocks Set',cat:'Toys',price:1299},
      {id:6,title:'Running Shoes',cat:'Clothing',price:2599},
      {id:7,title:'Coffee Maker',cat:'Home',price:3499},
      {id:8,title:'Bluetooth Speaker',cat:'Electronics',price:1299}
    ];

    let cart = {};
    const productGrid = document.getElementById('productGrid');
    const productCount = document.getElementById('productCount');
    const cartList = document.getElementById('cartList');
    const cartTotal = document.getElementById('cartTotal');
    const cartCount = document.getElementById('cartCount');

    function renderProducts(list){
      productGrid.innerHTML='';
      list.forEach(p=>{
        const card = document.createElement('div');card.className='card';
        card.innerHTML = `
          <div class="thumb">${p.title.split(' ').slice(0,2).join(' ')}<div style="font-size:12px;color:var(--muted);margin-top:6px">${p.cat}</div></div>
          <div class="title">${p.title}</div>
          <div class="price">₹${p.price.toLocaleString()}</div>
          <div class="meta">
            <div style="font-size:13px;color:var(--muted)">In stock</div>
            <button class="btn" onclick='addToCart(${p.id})'>Add</button>
          </div>`;
        productGrid.appendChild(card);
      });
      productCount.textContent = list.length;
    }

    function addToCart(id){
      const p = products.find(x=>x.id===id);
      if(!cart[id]) cart[id]={...p,qty:0};
      cart[id].qty++;
      renderCart();
    }

    function renderCart(){
      cartList.innerHTML='';
      const keys = Object.keys(cart);
      if(keys.length===0){cartList.innerHTML='<div style="color:var(--muted)">Cart is empty — add something!</div>'}
      let total=0;let count=0;
      keys.forEach(k=>{
        const it = cart[k]; total += it.price * it.qty; count += it.qty;
        const row = document.createElement('div'); row.className='cart-item';
        row.innerHTML = `<div style="width:48px;height:48px;border-radius:8px;background:#f1f5f9;display:flex;align-items:center;justify-content:center;font-weight:700">${it.title.split(' ')[0]}</div>
          <div style="flex:1">
            <div style="font-weight:700">${it.title}</div>
            <div class="q">₹${it.price} × ${it.qty}</div>
          </div>
          <div style="display:flex;flex-direction:column;gap:6px">
            <button onclick='changeQty(${it.id},1)' style="padding:6px 8px;border-radius:8px">+</button>
            <button onclick='changeQty(${it.id},-1)' style="padding:6px 8px;border-radius:8px">−</button>
          </div>`;
        cartList.appendChild(row);
      });
      cartTotal.textContent = '₹' + total.toLocaleString();
      cartCount.textContent = count;
    }

    function changeQty(id,delta){
      if(!cart[id]) return;
      cart[id].qty += delta;
      if(cart[id].qty<=0) delete cart[id];
      renderCart();
    }

    function filterCategory(cat){
      if(cat==='All') renderProducts(products);
      else renderProducts(products.filter(p=>p.cat===cat));
    }

    function toggleCart(){
      const el = document.getElementById('cartPanel');
      el.style.display = (el.style.display === 'none') ? 'flex' : 'flex';
      // On small screens we could scroll to it
      el.scrollIntoView({behavior:'smooth'});
    }

    function checkout(){
      if(Object.keys(cart).length===0){alert('Cart is empty. Add items before checking out.');return}
      alert('Demo checkout — total ' + cartTotal.textContent + "\nThanks for trying this template!");
      cart = {}; renderCart();
    }

    // Search box
    document.getElementById('searchBox').addEventListener('input',(e)=>{
      const q = e.target.value.trim().toLowerCase();
      if(!q) renderProducts(products);
      else renderProducts(products.filter(p=>p.title.toLowerCase().includes(q) || p.cat.toLowerCase().includes(q)));
    });

    // initial
    renderProducts(products);
    renderCart();
  </script>
</body>
</html>
