تمام! هنا ملف `index.html` كامل جاهز للتحميل والرفع:

---

### محتوى ملف `index.html`

```html
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>متجر ASO</title>
  <style>
    /* Reset */
    * {
      margin: 0; padding: 0; box-sizing: border-box;
    }
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #121212;
      color: #eee;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }
    header {
      background: linear-gradient(90deg, #0d47a1, #f44336);
      padding: 20px;
      text-align: center;
      font-size: 2.5rem;
      font-weight: bold;
      letter-spacing: 4px;
      color: white;
      user-select: none;
    }
    nav {
      background: #1f1f1f;
      display: flex;
      justify-content: center;
      gap: 30px;
      padding: 15px 0;
      font-weight: 600;
    }
    nav a {
      color: #eee;
      text-decoration: none;
      font-size: 1.1rem;
      transition: color 0.3s ease;
    }
    nav a:hover {
      color: #f44336;
    }
    main {
      flex: 1;
      max-width: 1200px;
      margin: 30px auto;
      padding: 0 20px;
      display: grid;
      grid-template-columns: 3fr 1fr;
      gap: 40px;
    }
    /* منتجات */
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px,1fr));
      gap: 25px;
    }
    .product-card {
      background: #222;
      border-radius: 10px;
      padding: 15px;
      display: flex;
      flex-direction: column;
      align-items: center;
      transition: transform 0.3s ease;
      box-shadow: 0 4px 12px rgba(244,67,54,0.3);
    }
    .product-card:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 18px rgba(244,67,54,0.5);
    }
    .product-card img {
      max-width: 100%;
      border-radius: 10px;
      margin-bottom: 15px;
    }
    .product-card h3 {
      margin-bottom: 10px;
      color: #f44336;
    }
    .product-card p {
      flex: 1;
      font-size: 0.9rem;
      margin-bottom: 15px;
      color: #ccc;
      text-align: center;
    }
    .product-card button {
      background: #0d47a1;
      border: none;
      padding: 10px 18px;
      color: white;
      font-weight: 700;
      border-radius: 6px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .product-card button:hover {
      background: #f44336;
    }
    /* سلة المشتريات */
    aside.cart {
      background: #1e1e1e;
      border-radius: 12px;
      padding: 20px;
      height: fit-content;
      box-shadow: 0 0 15px rgba(244,67,54,0.4);
      display: flex;
      flex-direction: column;
    }
    aside.cart h2 {
      margin-bottom: 20px;
      text-align: center;
      color: #f44336;
    }
    .cart-items {
      flex-grow: 1;
      max-height: 300px;
      overflow-y: auto;
      margin-bottom: 15px;
    }
    .cart-item {
      display: flex;
      justify-content: space-between;
      background: #2a2a2a;
      padding: 10px;
      border-radius: 6px;
      margin-bottom: 10px;
      align-items: center;
      font-size: 0.95rem;
    }
    .cart-item button.remove {
      background: transparent;
      border: none;
      color: #f44336;
      font-weight: 700;
      cursor: pointer;
      font-size: 1.1rem;
    }
    .cart-total {
      font-weight: 700;
      font-size: 1.2rem;
      text-align: center;
      margin-bottom: 15px;
      color: #f44336;
    }
    .checkout-btn {
      background: #f44336;
      border: none;
      color: white;
      padding: 12px;
      font-weight: 700;
      font-size: 1.1rem;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.3s ease;
    }
    .checkout-btn:hover {
      background: #d32f2f;
    }
    /* نموذج تواصل */
    section.contact {
      max-width: 1200px;
      margin: 40px auto 60px;
      padding: 0 20px;
      background: #222;
      border-radius: 12px;
      box-shadow: 0 0 15px rgba(244,67,54,0.4);
    }
    section.contact h2 {
      text-align: center;
      color: #f44336;
      margin-bottom: 25px;
    }
    form {
      display: flex;
      flex-direction: column;
      gap: 15px;
      max-width: 600px;
      margin: 0 auto 30px;
    }
    input, textarea {
      padding: 12px 15px;
      border-radius: 8px;
      border: none;
      font-size: 1rem;
      resize: vertical;
    }
    input:focus, textarea:focus {
      outline: 2px solid #f44336;
      background: #333;
      color: white;
    }
    button.send-btn {
      background: #f44336;
      color: white;
      border: none;
      font-weight: 700;
      padding: 14px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1.1rem;
      transition: background 0.3s ease;
    }
    button.send-btn:hover {
      background: #d32f2f;
    }
    /* طرق الدفع */
    .payment-methods {
      display: flex;
      justify-content: center;
      gap: 25px;
      margin-top: 20px;
    }
    .payment-methods img {
      width: 60px;
      filter: brightness(0) invert(1);
      transition: transform 0.3s ease;
      cursor: pointer;
    }
    .payment-methods img:hover {
      transform: scale(1.1);
    }
    /* Responsive */
    @media (max-width: 900px) {
      main {
        grid-template-columns: 1fr;
      }
      aside.cart {
        margin-top: 40px;
      }
    }
  </style>
</head>
<body>

<header>ASO - المتجر الإلكتروني</header>
<nav>
  <a href="#products-section">المنتجات</a>
  <a href="#contact-section">تواصل معنا</a>
</nav>

<main>
  <section class="products" id="products-section">
    <!-- المنتجات ستضاف جافاسكريبت -->
  </section>

  <aside class="cart">
    <h2>سلة المشتريات</h2>
    <div class="cart-items"></div>
    <div class="cart-total">الإجمالي: 0 د.إ</div>
    <button class="checkout-btn">الدفع</button>
    <div class="payment-methods" title="طرق الدفع">
      <img src="https://img.icons8.com/color/48/000000/visa.png" alt="Visa" />
      <img src="https://img.icons8.com/color/48/000000/mastercard.png" alt="MasterCard" />
      <img src="https://img.icons8.com/color/48/000000/paypal.png" alt="PayPal" />
      <img src="https://img.icons8.com/color/48/000000/apple-pay.png" alt="Apple Pay" />
    </div>
  </aside>
</main>

<section class="contact" id="contact-section">
  <h2>تواصل معنا</h2>
  <form id="contact-form">
    <input type="text" id="name" placeholder="اسمك" required />
    <input type="email" id="email" placeholder="بريدك الإلكتروني" required />
    <textarea id="message" rows="5" placeholder="رسالتك" required></textarea>
    <button type="submit" class="send-btn">أرسل</button>
  </form>
</section>

<script>
  // بيانات المنتجات
  const products = [
    {
      id: 1,
      name: "ساعة ذكية",
      description: "ساعة ذكية حديثة مع ميزات متعددة.",
      price: 350,
      img: "https://images.unsplash.com/photo-1517433456452-f9633a875f6f?auto=format&fit=crop&w=400&q=80"
    },
    {
      id: 2,
      name: "سماعات لاسلكية",
      description: "سماعات عالية الجودة مع عزل للضوضاء.",
      price: 150,
      img: "https://images.unsplash.com/photo-1512499617640-c2f99995e371?auto=format&fit=crop&w=400&q=80"
    },
    {
      id: 3,
      name: "هاتف ذكي",
      description: "هاتف ذكي بمواصفات رائعة وكاميرا مميزة.",
      price: 1200,
      img: "https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?auto=format&fit=crop&w=400&q=80"
    },
    {
      id: 4,
      name: "لوحة مفاتيح ميكانيكية",
      description: "لوحة مفاتيح للألعاب مع إضاءة خلفية.",
      price: 200,
      img: "https://images.unsplash.com/photo-1517336714731-489689fd1ca8?auto=format&fit=crop&w=400&q=80"
    }
  ];

  const productsContainer = document.querySelector('.products');
  const cartItemsContainer = document.querySelector('.cart-items');
  const cartTotalElem = document.querySelector('.cart-total');
  const checkoutBtn = document.querySelector('.checkout-btn');

  let cart = [];

  function updateCartUI() {
    cartItemsContainer.innerHTML = '';
    let total = 0;
    cart.forEach(item => {
      total += item.price * item.quantity;
      const cartItem = document.createElement('div');
      cartItem.className = 'cart-item';
      cartItem.innerHTML = `
        <span>${item.name} × ${item.quantity}</span>
        <div>
          <span>${item.price * item.quantity} د.إ</span>
          <button class="remove" data-id="${item.id}">&times;</button>
        </div>
      `;
      cartItemsContainer.appendChild(cartItem);
    });
    cartTotalElem.textContent = `الإجمالي: ${total} د.إ`;
    if (cart.length === 0) {
      cartItemsContainer.innerHTML = '<p style="text-align:center;color:#999;">السلة فارغة</p>';
      checkoutBtn.disabled = true;
      checkoutBtn.style.opacity = 0.6;
    } else {
      checkoutBtn.disabled = false;
      checkoutBtn.style.opacity = 1;
    }
  }

  // إضافة منتج للسلة
  function addToCart(id) {
    const product = products.find(p => p.id === id);
    if (!product) return;
    const exist = cart.find(i => i.id === id);
    if (exist) {
      exist.quantity++;
    } else {
      cart.push({...product, quantity: 1});
    }
    updateCartUI();
  }

  // إزالة منتج من السلة
  cartItemsContainer.addEventListener('click', e => {
    if (e.target.classList.contains('remove')) {
      const id = parseInt(e.target.dataset.id);
      cart = cart.filter(item => item.id !== id);
      updateCartUI();
    }
  });

  // عرض المنتجات
  function renderProducts() {
    products.forEach(product => {
      const card = document.createElement('div');
      card.className = 'product-card';
      card.innerHTML = `
        <img src="${product.img}" alt="${product.name}" />
        <h3>${product.name}</h3>
        <p>${product.description}</p>
        <button onclick="addToCart(${product.id})">أضف للسلة - ${product.price} د.إ</button>
      `;
      productsContainer.appendChild(card);
    });
  }

  renderProducts();
  updateCartUI();

  // نموذج تواصل (بسيط)
  const contactForm = document.getElementById('contact-form');
  contactForm.addEventListener('submit', e => {
    e.preventDefault();
    alert(`شكراً لتواصلك معنا، ${contactForm.name.value}! سنرد عليك قريباً.`);
    contactForm.reset();
  });

  // دفع (مجرد رسالة)
  checkoutBtn.addEventListener('click', () => {
    if (cart.length === 0) return;
    alert('تم استلام طلبك بنجاح! شكراً لتسوقك معنا.');
    cart = [];
    updateCartUI();
  });
</script>

</body>
</html>
```
