<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>VELOUR — Fragancias con Descuento | Chile</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;1,300&family=Cinzel:wght@400;500&family=Jost:wght@200;300;400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
:root{
  --ivory:#f8f4ee;--cream:#ede8df;--gold:#b89a6a;--gold-lt:#d4b87a;
  --dark:#1a1612;--mid:#3a3028;--text:#4a3f32;--subtle:#9a8f82;
  --line:rgba(184,154,106,0.2);--red:#c0392b;--green:#27ae60;
  --silk:#e8f4fd;--elite:#fdf4e8;
}
html{scroll-behavior:smooth}
body{font-family:'Jost',sans-serif;background:var(--ivory);color:var(--text);overflow-x:hidden}

/* SCROLLBAR */
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:var(--cream)}
::-webkit-scrollbar-thumb{background:var(--gold);border-radius:2px}

/* ── TOP BAR ── */
.topbar{background:var(--dark);padding:8px 40px;display:flex;justify-content:space-between;align-items:center}
.topbar-msg{font-size:.62rem;letter-spacing:.3em;color:var(--gold-lt);text-transform:uppercase}
.topbar-links{display:flex;gap:20px}
.topbar-links a{font-size:.6rem;letter-spacing:.2em;color:rgba(248,244,238,.4);text-decoration:none;transition:color .3s}
.topbar-links a:hover{color:var(--gold)}

/* ── NAV ── */
nav{position:sticky;top:0;z-index:200;background:rgba(248,244,238,.95);backdrop-filter:blur(12px);border-bottom:1px solid var(--line);padding:0 40px}
.nav-inner{display:flex;align-items:center;justify-content:space-between;height:68px}
.nav-logo{font-family:'Cinzel',serif;font-size:1.4rem;letter-spacing:.3em;color:var(--dark);text-decoration:none;cursor:pointer}
.nav-logo span{color:var(--gold)}
.nav-tabs{display:flex;gap:0;border-left:1px solid var(--line)}
.nav-tab{padding:0 24px;height:68px;display:flex;align-items:center;font-size:.68rem;letter-spacing:.2em;text-transform:uppercase;font-weight:300;color:var(--subtle);border:none;background:none;cursor:pointer;border-right:1px solid var(--line);transition:all .3s;white-space:nowrap}
.nav-tab:hover,.nav-tab.active{color:var(--dark);background:var(--cream)}
.nav-tab.active{border-bottom:2px solid var(--gold)}
.nav-right{display:flex;align-items:center;gap:16px}
.cart-btn{display:flex;align-items:center;gap:8px;background:var(--dark);color:var(--ivory);border:none;padding:10px 20px;font-family:'Jost',sans-serif;font-size:.68rem;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;transition:background .3s;position:relative}
.cart-btn:hover{background:var(--gold)}
.cart-count{background:var(--gold);color:var(--dark);border-radius:50%;width:18px;height:18px;display:flex;align-items:center;justify-content:center;font-size:.6rem;font-weight:500}

/* ── HERO BANNER ── */
.hero-banner{background:linear-gradient(135deg,var(--dark) 0%,#2a2018 60%,#1a1200 100%);padding:60px 40px;display:grid;grid-template-columns:1fr auto;gap:40px;align-items:center;position:relative;overflow:hidden}
.hero-banner::before{content:'';position:absolute;right:0;top:0;width:50%;height:100%;background:radial-gradient(ellipse at right center,rgba(184,154,106,.12),transparent 70%)}
.hero-eyebrow{font-size:.6rem;letter-spacing:.5em;text-transform:uppercase;color:var(--gold);margin-bottom:12px}
.hero-title{font-family:'Cormorant Garamond',serif;font-size:clamp(2rem,4vw,3.5rem);font-weight:300;color:var(--ivory);line-height:1.1;margin-bottom:16px}
.hero-title em{color:var(--gold);font-style:italic}
.hero-sub{font-size:.82rem;font-weight:200;letter-spacing:.08em;color:rgba(248,244,238,.55);max-width:500px;line-height:1.9}
.hero-badges{display:flex;gap:12px;margin-top:24px;flex-wrap:wrap}
.badge{padding:6px 16px;border:1px solid rgba(184,154,106,.4);font-size:.58rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold-lt)}
.hero-stats{display:flex;flex-direction:column;gap:20px;text-align:center;min-width:160px}
.stat-box{background:rgba(255,255,255,.04);border:1px solid rgba(184,154,106,.15);padding:20px}
.stat-n{font-family:'Cormorant Garamond',serif;font-size:2rem;color:var(--gold);font-weight:300}
.stat-l{font-size:.58rem;letter-spacing:.3em;text-transform:uppercase;color:rgba(248,244,238,.4);margin-top:4px}

/* ── PAGES ── */
.page{display:none;padding:40px}
.page.active{display:block}

/* ── FILTERS ── */
.filters-bar{display:flex;gap:12px;margin-bottom:32px;flex-wrap:wrap;align-items:center}
.filter-btn{padding:8px 20px;border:1px solid var(--line);background:none;font-family:'Jost',sans-serif;font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;color:var(--subtle);cursor:pointer;transition:all .3s}
.filter-btn:hover,.filter-btn.active{background:var(--dark);color:var(--ivory);border-color:var(--dark)}
.filter-source{padding:8px 16px;border:1px solid var(--line);background:none;font-size:.65rem;letter-spacing:.15em;color:var(--text);cursor:pointer;font-family:'Jost',sans-serif}
.search-box{padding:9px 18px;border:1px solid var(--line);background:transparent;font-family:'Jost',sans-serif;font-size:.78rem;color:var(--text);flex:1;max-width:280px;outline:none}
.search-box:focus{border-color:var(--gold)}
.results-count{font-size:.7rem;letter-spacing:.15em;color:var(--subtle);margin-left:auto}

/* ── PRODUCT GRID ── */
.products-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:2px}
.prod-card{background:var(--ivory);border:1px solid var(--line);overflow:hidden;transition:box-shadow .3s;position:relative}
.prod-card:hover{box-shadow:0 8px 40px rgba(0,0,0,.1)}
.prod-image{height:200px;display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
.prod-img-bg{position:absolute;inset:0;transition:transform .5s ease}
.prod-card:hover .prod-img-bg{transform:scale(1.05)}
.prod-badges{position:absolute;top:12px;left:12px;display:flex;flex-direction:column;gap:6px;z-index:2}
.badge-dcto{background:var(--red);color:white;font-size:.6rem;letter-spacing:.2em;padding:4px 10px;font-weight:500}
.badge-source{font-size:.55rem;letter-spacing:.2em;padding:3px 8px;font-weight:300}
.badge-silk{background:#0077b6;color:white}
.badge-elite{background:#8b5e3c;color:white}
.prod-body{padding:20px}
.prod-brand{font-size:.58rem;letter-spacing:.35em;text-transform:uppercase;color:var(--gold);margin-bottom:6px}
.prod-name{font-family:'Cormorant Garamond',serif;font-size:1.15rem;font-weight:300;color:var(--dark);margin-bottom:4px;line-height:1.3}
.prod-ml{font-size:.65rem;font-weight:200;color:var(--subtle);margin-bottom:12px}
.prod-prices{display:flex;align-items:baseline;gap:10px;margin-bottom:8px}
.prod-price-original{font-size:.75rem;color:var(--subtle);text-decoration:line-through}
.prod-price-source{font-size:.85rem;color:var(--gold);font-weight:400}
.prod-price-our{font-family:'Cormorant Garamond',serif;font-size:1.4rem;color:var(--dark);font-weight:400}
.prod-margin-note{font-size:.6rem;color:var(--green);letter-spacing:.15em;margin-bottom:14px}
.prod-actions{display:flex;gap:8px}
.btn-cart{flex:1;padding:10px;background:var(--dark);color:var(--ivory);border:none;font-family:'Jost',sans-serif;font-size:.62rem;letter-spacing:.25em;text-transform:uppercase;cursor:pointer;transition:background .3s}
.btn-cart:hover{background:var(--gold)}
.btn-buy{padding:10px 16px;background:none;border:1px solid var(--gold);color:var(--gold);font-family:'Jost',sans-serif;font-size:.62rem;letter-spacing:.2em;cursor:pointer;transition:all .3s;text-transform:uppercase}
.btn-buy:hover{background:var(--gold);color:var(--ivory)}

/* ── CART PANEL ── */
.cart-overlay{position:fixed;inset:0;background:rgba(0,0,0,.5);z-index:300;display:none;backdrop-filter:blur(4px)}
.cart-overlay.open{display:block}
.cart-panel{position:fixed;right:0;top:0;bottom:0;width:460px;background:var(--ivory);z-index:301;transform:translateX(100%);transition:transform .4s ease;display:flex;flex-direction:column}
.cart-panel.open{transform:translateX(0)}
.cart-header{padding:28px 32px;border-bottom:1px solid var(--line);display:flex;justify-content:space-between;align-items:center}
.cart-title{font-family:'Cinzel',serif;font-size:.9rem;letter-spacing:.3em;color:var(--dark)}
.cart-close{background:none;border:none;font-size:1.2rem;cursor:pointer;color:var(--subtle)}
.cart-items{flex:1;overflow-y:auto;padding:24px 32px}
.cart-empty{text-align:center;padding:60px 0;color:var(--subtle)}
.cart-empty-icon{font-size:3rem;margin-bottom:16px}
.cart-item{display:flex;gap:16px;padding:16px 0;border-bottom:1px solid var(--line)}
.cart-item-img{width:60px;height:80px;background:var(--cream);flex-shrink:0;display:flex;align-items:center;justify-content:center;font-size:.6rem;color:var(--subtle)}
.cart-item-info{flex:1}
.cart-item-name{font-family:'Cormorant Garamond',serif;font-size:1rem;color:var(--dark);margin-bottom:4px}
.cart-item-sub{font-size:.62rem;color:var(--subtle);letter-spacing:.1em;margin-bottom:8px}
.cart-item-price{font-size:.9rem;color:var(--gold);font-weight:400}
.cart-item-remove{background:none;border:none;color:var(--subtle);cursor:pointer;font-size:.8rem;padding:4px}
.cart-item-remove:hover{color:var(--red)}
.cart-footer{padding:24px 32px;border-top:1px solid var(--line);background:var(--cream)}
.cart-subtotal{display:flex;justify-content:space-between;margin-bottom:8px}
.cart-subtotal-label{font-size:.72rem;letter-spacing:.2em;text-transform:uppercase;color:var(--subtle)}
.cart-subtotal-val{font-family:'Cormorant Garamond',serif;font-size:1.2rem;color:var(--dark)}
.cart-savings{display:flex;justify-content:space-between;margin-bottom:20px;padding:10px;background:rgba(39,174,96,.08);border:1px solid rgba(39,174,96,.2)}
.cart-savings-label{font-size:.62rem;letter-spacing:.15em;color:var(--green)}
.cart-savings-val{font-size:.82rem;color:var(--green);font-weight:500}
.btn-checkout{width:100%;padding:16px;background:var(--dark);color:var(--ivory);border:none;font-family:'Jost',sans-serif;font-size:.72rem;letter-spacing:.3em;text-transform:uppercase;cursor:pointer;transition:background .3s;margin-bottom:10px}
.btn-checkout:hover{background:var(--gold)}
.btn-checkout-secondary{width:100%;padding:12px;background:none;border:1px solid var(--line);color:var(--text);font-family:'Jost',sans-serif;font-size:.65rem;letter-spacing:.2em;text-transform:uppercase;cursor:pointer;transition:all .3s}
.btn-checkout-secondary:hover{border-color:var(--gold);color:var(--gold)}

/* ── CHECKOUT MODAL ── */
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,.6);z-index:400;display:none;align-items:center;justify-content:center;padding:20px;backdrop-filter:blur(6px)}
.modal-overlay.open{display:flex}
.modal{background:var(--ivory);width:100%;max-width:640px;max-height:90vh;overflow-y:auto;position:relative}
.modal-header{padding:32px 40px 20px;border-bottom:1px solid var(--line);display:flex;justify-content:space-between;align-items:center;position:sticky;top:0;background:var(--ivory);z-index:1}
.modal-title{font-family:'Cinzel',serif;font-size:1rem;letter-spacing:.3em;color:var(--dark)}
.modal-step{font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold)}
.modal-close{background:none;border:none;font-size:1.4rem;cursor:pointer;color:var(--subtle)}
.modal-body{padding:32px 40px}
.step-indicator{display:flex;gap:0;margin-bottom:36px}
.step-dot{flex:1;height:3px;background:var(--line);position:relative;transition:background .4s}
.step-dot.done{background:var(--gold)}
.step-dot::after{content:attr(data-label);position:absolute;top:10px;left:0;font-size:.55rem;letter-spacing:.2em;text-transform:uppercase;color:var(--subtle);white-space:nowrap}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px}
.form-group{display:flex;flex-direction:column;gap:6px;margin-bottom:16px}
.form-group.full{grid-column:1/-1}
.form-label{font-size:.62rem;letter-spacing:.25em;text-transform:uppercase;color:var(--subtle)}
.form-input{padding:12px 16px;border:1px solid var(--line);background:transparent;font-family:'Jost',sans-serif;font-size:.82rem;color:var(--text);outline:none;transition:border-color .3s}
.form-input:focus{border-color:var(--gold)}
.form-select{padding:12px 16px;border:1px solid var(--line);background:var(--ivory);font-family:'Jost',sans-serif;font-size:.82rem;color:var(--text);outline:none;cursor:pointer}
.source-selector{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:20px}
.source-option{padding:16px;border:2px solid var(--line);cursor:pointer;transition:all .3s;text-align:center}
.source-option:hover{border-color:var(--gold)}
.source-option.selected{border-color:var(--gold);background:rgba(184,154,106,.06)}
.source-logo{font-family:'Cinzel',serif;font-size:.8rem;letter-spacing:.2em;margin-bottom:4px}
.source-desc{font-size:.6rem;color:var(--subtle);letter-spacing:.1em}
.order-summary-box{background:var(--cream);padding:20px;margin-bottom:20px}
.order-row{display:flex;justify-content:space-between;padding:8px 0;border-bottom:1px solid var(--line);font-size:.78rem}
.order-row:last-child{border:none;font-weight:500;font-size:.9rem}
.btn-next{width:100%;padding:16px;background:var(--dark);color:var(--ivory);border:none;font-family:'Jost',sans-serif;font-size:.72rem;letter-spacing:.3em;text-transform:uppercase;cursor:pointer;transition:background .3s;margin-top:12px}
.btn-next:hover{background:var(--gold)}
.btn-back{width:100%;padding:12px;background:none;border:1px solid var(--line);color:var(--subtle);font-family:'Jost',sans-serif;font-size:.65rem;letter-spacing:.2em;cursor:pointer;margin-bottom:10px}
.confirmation-box{text-align:center;padding:40px 0}
.confirm-icon{font-size:3rem;margin-bottom:20px}
.confirm-title{font-family:'Cormorant Garamond',serif;font-size:1.8rem;color:var(--dark);margin-bottom:12px}
.confirm-sub{font-size:.82rem;color:var(--subtle);line-height:1.8;margin-bottom:28px}
.confirm-order-id{display:inline-block;padding:10px 24px;border:1px solid var(--gold);font-family:'Cinzel',serif;font-size:.8rem;letter-spacing:.3em;color:var(--gold);margin-bottom:28px}
.automation-flow{background:var(--dark);padding:24px;text-align:left;margin-bottom:24px}
.flow-title{font-size:.6rem;letter-spacing:.4em;text-transform:uppercase;color:var(--gold);margin-bottom:16px}
.flow-step{display:flex;align-items:flex-start;gap:12px;padding:10px 0;border-bottom:1px solid rgba(255,255,255,.06)}
.flow-step:last-child{border:none}
.flow-num{width:22px;height:22px;border:1px solid var(--gold);border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:.6rem;color:var(--gold);flex-shrink:0;margin-top:2px}
.flow-text{font-size:.72rem;font-weight:200;color:rgba(248,244,238,.6);letter-spacing:.05em;line-height:1.6}
.flow-text strong{color:var(--gold-lt)}

/* ── COMPLAINTS PAGE ── */
.complaints-layout{display:grid;grid-template-columns:1fr 1.4fr;gap:32px}
.complaints-form-card,.complaints-list-card{background:white;border:1px solid var(--line);padding:32px}
.card-title{font-family:'Cinzel',serif;font-size:.85rem;letter-spacing:.3em;color:var(--dark);margin-bottom:24px;padding-bottom:16px;border-bottom:1px solid var(--line)}
.complaint-item{padding:16px;border:1px solid var(--line);margin-bottom:12px;position:relative}
.complaint-header{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:10px}
.complaint-id{font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--gold)}
.complaint-status{font-size:.58rem;letter-spacing:.2em;padding:4px 12px;text-transform:uppercase;font-weight:400}
.status-open{background:rgba(192,57,43,.1);color:var(--red);border:1px solid rgba(192,57,43,.2)}
.status-progress{background:rgba(184,154,106,.1);color:var(--gold);border:1px solid rgba(184,154,106,.2)}
.status-resolved{background:rgba(39,174,96,.1);color:var(--green);border:1px solid rgba(39,174,96,.2)}
.complaint-name{font-size:.82rem;font-weight:400;color:var(--dark);margin-bottom:4px}
.complaint-desc{font-size:.75rem;font-weight:200;color:var(--subtle);line-height:1.6;margin-bottom:10px}
.complaint-meta{font-size:.6rem;letter-spacing:.15em;color:var(--subtle)}
.complaint-actions{display:flex;gap:8px;margin-top:12px}
.btn-resolve{padding:6px 14px;background:none;border:1px solid var(--green);color:var(--green);font-size:.58rem;letter-spacing:.2em;cursor:pointer;text-transform:uppercase;transition:all .3s}
.btn-resolve:hover{background:var(--green);color:white}
.btn-progress{padding:6px 14px;background:none;border:1px solid var(--gold);color:var(--gold);font-size:.58rem;letter-spacing:.2em;cursor:pointer;text-transform:uppercase;transition:all .3s}
.btn-progress:hover{background:var(--gold);color:white}
.stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-bottom:28px}
.stat-card{padding:20px;background:var(--cream);text-align:center}
.stat-card-num{font-family:'Cormorant Garamond',serif;font-size:2rem;color:var(--dark)}
.stat-card-label{font-size:.6rem;letter-spacing:.25em;text-transform:uppercase;color:var(--subtle);margin-top:4px}

/* ── ADMIN PANEL ── */
.admin-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(200px,1fr));gap:16px;margin-bottom:32px}
.admin-card{background:var(--dark);padding:24px;color:var(--ivory)}
.admin-card-val{font-family:'Cormorant Garamond',serif;font-size:2.2rem;color:var(--gold)}
.admin-card-label{font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:rgba(248,244,238,.4);margin-top:6px}
.admin-card-sub{font-size:.68rem;color:rgba(248,244,238,.25);margin-top:4px}
.orders-table{width:100%;border-collapse:collapse;background:white;font-size:.78rem}
.orders-table th{padding:14px 16px;text-align:left;font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--subtle);border-bottom:2px solid var(--line);font-weight:400;background:var(--cream)}
.orders-table td{padding:14px 16px;border-bottom:1px solid var(--line);color:var(--text)}
.orders-table tr:hover td{background:rgba(248,244,238,.5)}
.order-status{display:inline-block;padding:3px 10px;font-size:.58rem;letter-spacing:.15em;text-transform:uppercase;border-radius:0}
.os-pending{background:rgba(184,154,106,.1);color:var(--gold)}
.os-processing{background:rgba(52,152,219,.1);color:#2980b9}
.os-shipped{background:rgba(39,174,96,.1);color:var(--green)}
.os-delivered{background:rgba(0,0,0,.05);color:var(--mid)}
.profit-pill{display:inline-block;background:rgba(39,174,96,.1);color:var(--green);padding:2px 8px;font-size:.65rem;font-weight:500}

/* ── MARGIN CALCULATOR ── */
.calculator-card{background:white;border:1px solid var(--line);padding:40px;max-width:600px}
.calc-label{font-size:.62rem;letter-spacing:.25em;text-transform:uppercase;color:var(--subtle);margin-bottom:8px}
.calc-input{width:100%;padding:14px 18px;border:1px solid var(--line);font-family:'Jost',sans-serif;font-size:1rem;color:var(--dark);outline:none;transition:border-color .3s;margin-bottom:20px;background:var(--ivory)}
.calc-input:focus{border-color:var(--gold)}
.calc-result-box{background:var(--dark);padding:28px;margin-top:8px}
.calc-result-row{display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid rgba(255,255,255,.06);font-size:.8rem}
.calc-result-row:last-child{border:none;font-size:1rem;padding-top:16px}
.calc-label-r{color:rgba(248,244,238,.45);letter-spacing:.1em}
.calc-value-r{color:var(--ivory);font-weight:300}
.calc-value-highlight{color:var(--gold);font-family:'Cormorant Garamond',serif;font-size:1.4rem}
.calc-range-note{margin-top:16px;padding:12px 16px;border-left:2px solid var(--gold);background:rgba(184,154,106,.06);font-size:.72rem;color:var(--text);line-height:1.7}

/* ── TOAST ── */
.toast{position:fixed;bottom:32px;right:32px;background:var(--dark);color:var(--ivory);padding:16px 24px;font-size:.75rem;letter-spacing:.1em;z-index:500;transform:translateY(80px);opacity:0;transition:all .4s ease;max-width:320px;border-left:3px solid var(--gold)}
.toast.show{transform:translateY(0);opacity:1}

/* ── MISC ── */
.page-header{margin-bottom:36px}
.page-header .section-label{font-size:.6rem;letter-spacing:.5em;text-transform:uppercase;color:var(--gold);margin-bottom:10px}
.page-header h2{font-family:'Cormorant Garamond',serif;font-size:2.2rem;font-weight:300;color:var(--dark)}
.divider{height:1px;background:var(--line);margin:32px 0}
.no-results{text-align:center;padding:80px 0;color:var(--subtle)}
.no-results-icon{font-size:3rem;margin-bottom:16px}

/* RADIO */
input[type=radio]{accent-color:var(--gold)}
textarea.form-input{resize:vertical;min-height:100px}

@media(max-width:768px){
  .nav-tabs{display:none}
  .products-grid{grid-template-columns:repeat(auto-fill,minmax(200px,1fr))}
  .cart-panel{width:100%}
  .complaints-layout{grid-template-columns:1fr}
  .form-row{grid-template-columns:1fr}
  .hero-banner{grid-template-columns:1fr}
  .hero-stats{flex-direction:row;min-width:auto}
}
</style>
</head>
<body>

<!-- TOP BAR -->
<div class="topbar">
  <span class="topbar-msg">✦ Envío gratis desde $25.000 · Despacho a todo Chile · Perfumes 100% originales ✦</span>
  <div class="topbar-links">
    <a href="#" onclick="showPage('reclamos')">Postventa</a>
    <a href="#" onclick="showPage('admin')">Panel Admin</a>
  </div>
</div>

<!-- NAV -->
<nav>
  <div class="nav-inner">
    <a class="nav-logo" onclick="showPage('tienda')">VELOUR<span>.</span></a>
    <div class="nav-tabs">
      <button class="nav-tab active" onclick="showPage('tienda')">Tienda</button>
      <button class="nav-tab" onclick="showPage('calculadora')">Calculadora</button>
      <button class="nav-tab" onclick="showPage('reclamos')">Reclamos</button>
      <button class="nav-tab" onclick="showPage('admin')">Admin</button>
    </div>
    <div class="nav-right">
      <button class="cart-btn" onclick="toggleCart()">
        🛍 Carrito <span class="cart-count" id="cartCount">0</span>
      </button>
    </div>
  </div>
</nav>

<!-- HERO -->
<div class="hero-banner">
  <div>
    <p class="hero-eyebrow">— Fragancias originales con descuento real</p>
    <h1 class="hero-title">Perfumes de <em>lujo</em><br/>al alcance de todos</h1>
    <p class="hero-sub">Seleccionamos los mejores descuentos de Silk Perfumes y Elite Perfumes. Tú compras aquí, nosotros gestionamos todo. Precios exclusivos, entrega garantizada.</p>
    <div class="hero-badges">
      <span class="badge">Silk Perfumes ↗</span>
      <span class="badge">Elite Perfumes ↗</span>
      <span class="badge">Hasta 70% dcto original</span>
      <span class="badge">Envío Bluexpress</span>
    </div>
  </div>
  <div class="hero-stats">
    <div class="stat-box"><div class="stat-n">70%</div><div class="stat-l">Dcto en origen</div></div>
    <div class="stat-box"><div class="stat-n">+80</div><div class="stat-l">Fragancias</div></div>
    <div class="stat-box"><div class="stat-n">2</div><div class="stat-l">Proveedores</div></div>
  </div>
</div>

<!-- ═══════════ PAGE: TIENDA ═══════════ -->
<div class="page active" id="page-tienda">
  <div class="filters-bar">
    <button class="filter-btn active" onclick="filterProducts('all',this)">Todos</button>
    <button class="filter-btn" onclick="filterProducts('mujer',this)">Mujer</button>
    <button class="filter-btn" onclick="filterProducts('hombre',this)">Hombre</button>
    <button class="filter-btn" onclick="filterProducts('unisex',this)">Unisex</button>
    <button class="filter-btn" onclick="filterProducts('set',this)">Sets</button>
    <select class="filter-source" onchange="filterSource(this.value)">
      <option value="all">Todos los proveedores</option>
      <option value="silk">Silk Perfumes</option>
      <option value="elite">Elite Perfumes</option>
    </select>
    <input class="search-box" type="text" placeholder="Buscar fragancia..." oninput="searchProducts(this.value)"/>
    <span class="results-count" id="resultsCount">Mostrando 24 productos</span>
  </div>
  <div class="products-grid" id="productsGrid"></div>
</div>

<!-- ═══════════ PAGE: CALCULADORA ═══════════ -->
<div class="page" id="page-calculadora">
  <div class="page-header">
    <p class="section-label">— Herramienta interna</p>
    <h2>Calculadora de Margen</h2>
  </div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:32px;align-items:start">
    <div class="calculator-card">
      <p class="calc-label">Precio original en tienda (Retail CLP)</p>
      <input class="calc-input" type="number" id="calcRetail" placeholder="Ej: 79.990" oninput="calcMargin()"/>
      <p class="calc-label">Precio con descuento en proveedor (CLP)</p>
      <input class="calc-input" type="number" id="calcSource" placeholder="Ej: 19.990" oninput="calcMargin()"/>
      <p class="calc-label">Tu precio de venta (CLP)</p>
      <input class="calc-input" type="number" id="calcSale" placeholder="Ej: 32.990" oninput="calcMargin()"/>
      <div class="calc-result-box" id="calcResult" style="display:none">
        <div class="calc-result-row"><span class="calc-label-r">Precio original retail</span><span class="calc-value-r" id="rRetail">-</span></div>
        <div class="calc-result-row"><span class="calc-label-r">Precio en proveedor</span><span class="calc-value-r" id="rSource">-</span></div>
        <div class="calc-result-row"><span class="calc-label-r">Tu precio de venta</span><span class="calc-value-r" id="rSale">-</span></div>
        <div class="calc-result-row"><span class="calc-label-r">Tu margen de ganancia</span><span class="calc-value-highlight" id="rMargin">-</span></div>
        <div class="calc-result-row"><span class="calc-label-r">% Dcto vs retail para cliente</span><span class="calc-value-r" id="rDcto">-</span></div>
        <div class="calc-result-row"><span class="calc-label-r">Estado del margen</span><span class="calc-value-r" id="rStatus">-</span></div>
      </div>
      <div class="calc-range-note">
        <strong>Regla de margen VELOUR:</strong> Agrega entre <strong>$10.000 – $15.000 CLP</strong> sobre el precio del proveedor. Tu precio debe quedar siempre por debajo del precio retail oficial para que el cliente perciba ahorro real.
      </div>
    </div>
    <div>
      <div class="calculator-card" style="margin-bottom:20px">
        <p style="font-family:'Cinzel',serif;font-size:.8rem;letter-spacing:.3em;color:var(--dark);margin-bottom:20px">Ejemplos Reales</p>
        <div style="display:flex;flex-direction:column;gap:12px" id="examplesList"></div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════ PAGE: RECLAMOS ═══════════ -->
<div class="page" id="page-reclamos">
  <div class="page-header">
    <p class="section-label">— Servicio Postventa</p>
    <h2>Gestión de Reclamos</h2>
  </div>
  <div class="stats-row">
    <div class="stat-card"><div class="stat-card-num" id="totalComplaints">0</div><div class="stat-card-label">Total reclamos</div></div>
    <div class="stat-card"><div class="stat-card-num" id="openComplaints">0</div><div class="stat-card-label">Abiertos</div></div>
    <div class="stat-card"><div class="stat-card-num" id="resolvedComplaints">0</div><div class="stat-card-label">Resueltos</div></div>
  </div>
  <div class="complaints-layout">
    <div class="complaints-form-card">
      <div class="card-title">Nuevo Reclamo</div>
      <div class="form-group">
        <label class="form-label">Nombre del cliente</label>
        <input class="form-input" id="cName" placeholder="Nombre completo"/>
      </div>
      <div class="form-group">
        <label class="form-label">N° de Orden</label>
        <input class="form-input" id="cOrder" placeholder="VLR-XXXXX"/>
      </div>
      <div class="form-group">
        <label class="form-label">Tipo de reclamo</label>
        <select class="form-select form-input" id="cType">
          <option>Producto no recibido</option>
          <option>Producto dañado</option>
          <option>Producto incorrecto</option>
          <option>Demora en entrega</option>
          <option>Solicitud de devolución</option>
          <option>Fragancia diferente a descripción</option>
          <option>Otro</option>
        </select>
      </div>
      <div class="form-group">
        <label class="form-label">Descripción del problema</label>
        <textarea class="form-input" id="cDesc" placeholder="Describe detalladamente el problema..."></textarea>
      </div>
      <div class="form-group">
        <label class="form-label">Proveedor involucrado</label>
        <select class="form-select form-input" id="cProvider">
          <option>Silk Perfumes</option>
          <option>Elite Perfumes</option>
          <option>No determinado</option>
        </select>
      </div>
      <button class="btn-next" onclick="submitComplaint()">Registrar Reclamo</button>
    </div>
    <div class="complaints-list-card">
      <div class="card-title">Reclamos Activos</div>
      <div id="complaintsList">
        <div class="no-results"><div class="no-results-icon">📋</div><p>No hay reclamos registrados</p></div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════ PAGE: ADMIN ═══════════ -->
<div class="page" id="page-admin">
  <div class="page-header">
    <p class="section-label">— Panel de control</p>
    <h2>Dashboard Dropshipping</h2>
  </div>
  <div class="admin-grid" id="adminStats"></div>
  <div style="background:white;border:1px solid var(--line);padding:28px">
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:20px">
      <p style="font-family:'Cinzel',serif;font-size:.82rem;letter-spacing:.3em;color:var(--dark)">Órdenes Recientes</p>
      <span style="font-size:.6rem;letter-spacing:.2em;text-transform:uppercase;color:var(--subtle)">Actualizado ahora</span>
    </div>
    <table class="orders-table" id="ordersTable">
      <thead>
        <tr>
          <th>Orden ID</th><th>Cliente</th><th>Producto</th><th>Proveedor</th>
          <th>Precio Venta</th><th>Ganancia</th><th>Estado</th>
        </tr>
      </thead>
      <tbody id="ordersBody"></tbody>
    </table>
    <div style="padding:16px;text-align:center;font-size:.7rem;color:var(--subtle);border-top:1px solid var(--line);margin-top:0" id="emptyOrders">
      Aún no hay órdenes. Las órdenes aparecerán aquí cuando los clientes compren.
    </div>
  </div>
</div>

<!-- ══════ CART PANEL ══════ -->
<div class="cart-overlay" id="cartOverlay" onclick="toggleCart()"></div>
<div class="cart-panel" id="cartPanel">
  <div class="cart-header">
    <span class="cart-title">Tu Carrito</span>
    <button class="cart-close" onclick="toggleCart()">✕</button>
  </div>
  <div class="cart-items" id="cartItems">
    <div class="cart-empty"><div class="cart-empty-icon">🛍</div><p>Tu carrito está vacío</p></div>
  </div>
  <div class="cart-footer" id="cartFooter" style="display:none">
    <div class="cart-subtotal">
      <span class="cart-subtotal-label">Subtotal</span>
      <span class="cart-subtotal-val" id="cartTotal">$0</span>
    </div>
    <div class="cart-savings">
      <span class="cart-savings-label">Tu ahorro vs retail</span>
      <span class="cart-savings-val" id="cartSavings">$0</span>
    </div>
    <button class="btn-checkout" onclick="openCheckout()">Proceder al Pago →</button>
    <button class="btn-checkout-secondary" onclick="toggleCart()">Seguir Comprando</button>
  </div>
</div>

<!-- ══════ CHECKOUT MODAL ══════ -->
<div class="modal-overlay" id="checkoutModal">
  <div class="modal">
    <div class="modal-header">
      <div>
        <div class="modal-step" id="stepLabel">Paso 1 de 3</div>
        <div class="modal-title" id="stepTitle">Datos de Envío</div>
      </div>
      <button class="modal-close" onclick="closeCheckout()">✕</button>
    </div>
    <div class="modal-body">
      <div class="step-indicator">
        <div class="step-dot done" data-label="Envío" id="dot1"></div>
        <div class="step-dot" data-label="Pago" id="dot2"></div>
        <div class="step-dot" data-label="Confirmar" id="dot3"></div>
      </div>

      <!-- Step 1: Shipping -->
      <div id="checkoutStep1">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Nombre</label>
            <input class="form-input" id="shipName" placeholder="Tu nombre"/>
          </div>
          <div class="form-group">
            <label class="form-label">Apellido</label>
            <input class="form-input" id="shipLastname" placeholder="Tu apellido"/>
          </div>
        </div>
        <div class="form-group">
          <label class="form-label">Email</label>
          <input class="form-input" type="email" id="shipEmail" placeholder="correo@ejemplo.com"/>
        </div>
        <div class="form-group">
          <label class="form-label">Teléfono</label>
          <input class="form-input" id="shipPhone" placeholder="+56 9 XXXX XXXX"/>
        </div>
        <div class="form-group">
          <label class="form-label">Dirección de envío</label>
          <input class="form-input" id="shipAddress" placeholder="Calle, número, depto"/>
        </div>
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">Ciudad</label>
            <input class="form-input" id="shipCity" placeholder="Santiago"/>
          </div>
          <div class="form-group">
            <label class="form-label">Región</label>
            <select class="form-select form-input" id="shipRegion">
              <option>Región Metropolitana</option>
              <option>Valparaíso</option>
              <option>Biobío</option>
              <option>Araucanía</option>
              <option>Los Lagos</option>
              <option>Antofagasta</option>
              <option>O'Higgins</option>
              <option>Maule</option>
              <option>Tarapacá</option>
              <option>Atacama</option>
              <option>Coquimbo</option>
              <option>Los Ríos</option>
              <option>Aysén</option>
              <option>Magallanes</option>
              <option>Arica y Parinacota</option>
              <option>Ñuble</option>
            </select>
          </div>
        </div>
        <div class="form-group">
          <label class="form-label" style="margin-bottom:12px">Proveedor de la compra</label>
          <div class="source-selector">
            <div class="source-option selected" onclick="selectSource('silk',this)">
              <div class="source-logo" style="color:#0077b6">SILK</div>
              <div class="source-desc">Silk Perfumes · Hasta 70% dcto</div>
            </div>
            <div class="source-option" onclick="selectSource('elite',this)">
              <div class="source-logo" style="color:#8b5e3c">ELITE</div>
              <div class="source-desc">Elite Perfumes · +600 fragancias</div>
            </div>
          </div>
          <p style="font-size:.62rem;color:var(--subtle);letter-spacing:.08em;line-height:1.7">La compra se realizará automáticamente en el proveedor con tu dirección. Tú recibes directamente, nosotros gestionamos todo.</p>
        </div>
        <button class="btn-next" onclick="nextStep(2)">Continuar →</button>
      </div>

      <!-- Step 2: Payment -->
      <div id="checkoutStep2" style="display:none">
        <div class="order-summary-box">
          <div class="order-row"><span>Subtotal</span><span id="s2Subtotal">-</span></div>
          <div class="order-row"><span>Envío Bluexpress</span><span style="color:var(--green)">GRATIS</span></div>
          <div class="order-row"><span>Total a pagar</span><span id="s2Total" style="color:var(--gold)">-</span></div>
        </div>
        <div class="form-group">
          <label class="form-label">Método de pago</label>
          <select class="form-select form-input" id="payMethod">
            <option>Tarjeta de crédito / débito</option>
            <option>Transferencia bancaria</option>
            <option>Webpay Plus</option>
            <option>MercadoPago</option>
          </select>
        </div>
        <div id="cardFields">
          <div class="form-group">
            <label class="form-label">Número de tarjeta</label>
            <input class="form-input" id="cardNum" placeholder="XXXX XXXX XXXX XXXX" maxlength="19" oninput="formatCard(this)"/>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">Vencimiento</label>
              <input class="form-input" id="cardExp" placeholder="MM/AA" maxlength="5"/>
            </div>
            <div class="form-group">
              <label class="form-label">CVV</label>
              <input class="form-input" id="cardCvv" placeholder="XXX" maxlength="4" type="password"/>
            </div>
          </div>
          <div class="form-group">
            <label class="form-label">Nombre en tarjeta</label>
            <input class="form-input" id="cardName" placeholder="Como aparece en la tarjeta"/>
          </div>
        </div>
        <button class="btn-back" onclick="nextStep(1)">← Volver</button>
        <button class="btn-next" onclick="nextStep(3)">Confirmar Orden →</button>
      </div>

      <!-- Step 3: Confirmation -->
      <div id="checkoutStep3" style="display:none">
        <div class="confirmation-box">
          <div class="confirm-icon">✅</div>
          <h3 class="confirm-title">¡Orden Confirmada!</h3>
          <p class="confirm-sub">Tu pedido ha sido procesado exitosamente. Recibirás un email de confirmación con el seguimiento de tu envío.</p>
          <div class="confirm-order-id" id="confirmOrderId">VLR-00000</div>
          <div class="automation-flow">
            <p class="flow-title">✦ Flujo automatizado activado</p>
            <div class="flow-step">
              <div class="flow-num">1</div>
              <div class="flow-text">Orden registrada en sistema VELOUR con ID único de seguimiento</div>
            </div>
            <div class="flow-step">
              <div class="flow-num">2</div>
              <div class="flow-text"><strong>Compra automática en proveedor</strong> con tu dirección de envío — no requiere tu intervención adicional</div>
            </div>
            <div class="flow-step">
              <div class="flow-num">3</div>
              <div class="flow-text">El proveedor (<strong id="flowProvider">Silk Perfumes</strong>) despacha directamente a tu domicilio vía Bluexpress</div>
            </div>
            <div class="flow-step">
              <div class="flow-num">4</div>
              <div class="flow-text">Recibirás código de seguimiento por email en las próximas 24 hrs hábiles</div>
            </div>
            <div class="flow-step">
              <div class="flow-num">5</div>
              <div class="flow-text">¿Problemas? Accede a <strong>Postventa</strong> en el menú con tu N° de orden</div>
            </div>
          </div>
          <button class="btn-next" onclick="finishOrder()">Perfecto, ¡gracias!</button>
        </div>
      </div>

    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
// ════════════════════════════════════
//  DATA — Products (based on Silk & Elite real catalog)
// ════════════════════════════════════
const PRODUCTS = [
  // SILK PERFUMES
  {id:1,source:'silk',gender:'mujer',brand:'Carolina Herrera',name:'Good Girl',ml:'80ml',type:'EDP',retail:89990,sourcePrice:22990,ourPrice:34990,notes:'Jazmín · Tonka · Tuberosa'},
  {id:2,source:'silk',gender:'mujer',brand:'Lancôme',name:'La Vie Est Belle',ml:'100ml',type:'EDP',retail:109990,sourcePrice:28990,ourPrice:39990,notes:'Iris · Pralinato · Vainilla'},
  {id:3,source:'silk',gender:'hombre',brand:'Paco Rabanne',name:'1 Million',ml:'100ml',type:'EDT',retail:79990,sourcePrice:19990,ourPrice:32990,notes:'Menta · Canela · Cuero'},
  {id:4,source:'silk',gender:'hombre',brand:'Dior',name:'Sauvage',ml:'100ml',type:'EDT',retail:119990,sourcePrice:34990,ourPrice:47990,notes:'Bergamota · Pimienta · Ambroxan'},
  {id:5,source:'silk',gender:'mujer',brand:'Yves Saint Laurent',name:'Black Opium',ml:'90ml',type:'EDP',retail:94990,sourcePrice:24990,ourPrice:36990,notes:'Café · Vainilla · Flor Blanca'},
  {id:6,source:'silk',gender:'hombre',brand:'Hugo Boss',name:'Bottled Night',ml:'100ml',type:'EDT',retail:59990,sourcePrice:14990,ourPrice:26990,notes:'Lavanda · Cardamomo · Sándalo'},
  {id:7,source:'silk',gender:'mujer',brand:'Chanel',name:'Chance Eau Tendre',ml:'100ml',type:'EDT',retail:129990,sourcePrice:38990,ourPrice:50990,notes:'Pomelo · Jazmín · Almizcle'},
  {id:8,source:'silk',gender:'unisex',brand:'Calvin Klein',name:'CK One',ml:'200ml',type:'EDT',retail:49990,sourcePrice:12990,ourPrice:24990,notes:'Bergamota · Violeta · Almizcle'},
  {id:9,source:'silk',gender:'hombre',brand:'Giorgio Armani',name:'Acqua di Giò',ml:'100ml',type:'EDT',retail:84990,sourcePrice:21990,ourPrice:34990,notes:'Mar · Limón · Cedro'},
  {id:10,source:'silk',gender:'mujer',brand:'Versace',name:'Bright Crystal',ml:'90ml',type:'EDT',retail:64990,sourcePrice:16990,ourPrice:28990,notes:'Granada · Peonía · Musgo'},
  {id:11,source:'silk',gender:'set',brand:'Britney Spears',name:'Midnight Fantasy',ml:'100ml Set',type:'EDP',retail:39990,sourcePrice:9990,ourPrice:21990,notes:'Uva · Frambuesa · Vainilla'},
  {id:12,source:'silk',gender:'hombre',brand:'Azzaro',name:'Chrome',ml:'100ml',type:'EDT',retail:54990,sourcePrice:13990,ourPrice:25990,notes:'Limón · Anís · Cuero'}  ,
  // ELITE PERFUMES
  {id:13,source:'elite',gender:'hombre',brand:'Lattafa',name:'Asad Zanzibar',ml:'100ml',type:'EDP',retail:39990,sourcePrice:15990,ourPrice:27990,notes:'Oud · Sándalo · Almizcle'},
  {id:14,source:'elite',gender:'mujer',brand:'Lattafa',name:'Fakhar Pride',ml:'100ml',type:'EDP',retail:33990,sourcePrice:19990,ourPrice:31990,notes:'Rosa · Iris · Madera'},
  {id:15,source:'elite',gender:'set',brand:'Tous',name:'Love Me Silver Set',ml:'90ml+4.5ml',type:'Parfum',retail:185990,sourcePrice:98990,ourPrice:112990,notes:'Bergamota · Frutos Rojos · Vainilla'},
  {id:16,source:'elite',gender:'hombre',brand:'Puig',name:'Quorum Silver Set',ml:'100ml+AfterShave',type:'EDT',retail:29990,sourcePrice:11961,ourPrice:23990,notes:'Madera · Cuero · Cítrico'},
  {id:17,source:'elite',gender:'set',brand:'Ariana Grande',name:'Thank U Next Set',ml:'10ml+10ml',type:'EDP',retail:29990,sourcePrice:19990,ourPrice:31990,notes:'Pera · Coco · Madera'},
  {id:18,source:'elite',gender:'unisex',brand:'Lattafa',name:'Badee Al Oud Sublime',ml:'100ml+Deo',type:'EDP',retail:43990,sourcePrice:31489,ourPrice:43990,notes:'Oud · Especias · Ámbar'},
  {id:19,source:'elite',gender:'mujer',brand:'Paco Rabanne',name:'Olympéa',ml:'80ml',type:'EDP',retail:89990,sourcePrice:24990,ourPrice:36990,notes:'Néroli · Sal · Vainilla'},
  {id:20,source:'elite',gender:'hombre',brand:'DKNY',name:'Be Delicious Men',ml:'100ml',type:'EDT',retail:69990,sourcePrice:17990,ourPrice:29990,notes:'Manzana · Madera · Almizcle'},
  {id:21,source:'elite',gender:'mujer',brand:'Tommy Hilfiger',name:'Tommy Girl',ml:'100ml',type:'EDT',retail:44990,sourcePrice:11990,ourPrice:23990,notes:'Manzana · Rosa · Sándalo'},
  {id:22,source:'elite',gender:'hombre',brand:'Calvin Klein',name:'Eternity For Men',ml:'100ml',type:'EDT',retail:64990,sourcePrice:16990,ourPrice:28990,notes:'Lavanda · Sándalo · Vetiver'},
  {id:23,source:'elite',gender:'mujer',brand:'Guess',name:'Seductive',ml:'75ml',type:'EDT',retail:39990,sourcePrice:9990,ourPrice:21990,notes:'Sandía · Lichi · Almizcle'},
  {id:24,source:'elite',gender:'unisex',brand:'Antonio Banderas',name:'The Golden Secret',ml:'100ml',type:'EDT',retail:29990,sourcePrice:7990,ourPrice:19990,notes:'Lavanda · Piña · Almizcle'}
];

// ════════════════════════════════════
//  STATE
// ════════════════════════════════════
let cart = [];
let complaints = [];
let orders = [];
let currentStep = 1;
let selectedSource = 'silk';
let activeFilter = 'all';
let activeSource = 'all';
let searchQuery = '';

// ════════════════════════════════════
//  NAVIGATION
// ════════════════════════════════════
function showPage(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('page-'+name).classList.add('active');
  document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t => {
    if(t.textContent.toLowerCase().includes(name==='tienda'?'tienda':name==='calculadora'?'calc':name==='reclamos'?'reclam':'admin')) t.classList.add('active');
  });
  if(name==='admin') renderAdmin();
  if(name==='calculadora') renderExamples();
}

// ════════════════════════════════════
//  PRODUCTS
// ════════════════════════════════════
function renderProducts() {
  const grid = document.getElementById('productsGrid');
  let filtered = PRODUCTS.filter(p => {
    const genderOk = activeFilter==='all' || p.gender===activeFilter;
    const sourceOk = activeSource==='all' || p.source===activeSource;
    const searchOk = searchQuery==='' || 
      p.name.toLowerCase().includes(searchQuery.toLowerCase()) ||
      p.brand.toLowerCase().includes(searchQuery.toLowerCase()) ||
      p.notes.toLowerCase().includes(searchQuery.toLowerCase());
    return genderOk && sourceOk && searchOk;
  });
  document.getElementById('resultsCount').textContent = `Mostrando ${filtered.length} producto${filtered.length!==1?'s':''}`;
  if(filtered.length===0){
    grid.innerHTML=`<div class="no-results" style="grid-column:1/-1"><div class="no-results-icon">🔍</div><p>No se encontraron productos</p></div>`;
    return;
  }
  grid.innerHTML = filtered.map(p => {
    const dcto = Math.round((1 - p.sourcePrice/p.retail)*100);
    const margin = p.ourPrice - p.sourcePrice;
    const savingsClient = p.retail - p.ourPrice;
    const colors = {silk:'#e8f4fd',elite:'#fdf4e8'};
    const svgBottle = `<svg viewBox="0 0 100 180" width="70" fill="none" xmlns="http://www.w3.org/2000/svg">
      <rect x="38" y="4" width="24" height="10" rx="1.5" fill="${p.source==='silk'?'#0077b6':'#8b5e3c'}" opacity=".7"/>
      <rect x="41" y="1" width="18" height="6" rx="1.5" fill="${p.source==='silk'?'#0077b6':'#8b5e3c'}"/>
      <rect x="40" y="14" width="20" height="20" rx="2" fill="#ede8df"/>
      <path d="M26 34 Q40 30 50 32 Q60 30 74 34 L78 44 H22 Z" fill="#f5ece0"/>
      <rect x="20" y="42" width="60" height="120" rx="5" fill="#f5ece0"/>
      <rect x="26" y="50" width="8" height="98" rx="4" fill="white" opacity=".2"/>
      <rect x="28" y="70" width="44" height="64" rx="2" fill="white" opacity=".6"/>
      <text x="50" y="95" font-family="serif" font-size="6" fill="#3a3028" text-anchor="middle" letter-spacing="1.5">${p.brand.toUpperCase().slice(0,8)}</text>
      <text x="50" y="107" font-family="serif" font-size="5" fill="#9a8f82" text-anchor="middle" font-style="italic">${p.name.slice(0,12)}</text>
      <text x="50" y="118" font-family="sans-serif" font-size="4" fill="${p.source==='silk'?'#0077b6':'#8b5e3c'}" text-anchor="middle" letter-spacing="1">${p.type}</text>
      <rect x="14" y="160" width="72" height="6" rx="3" fill="#d4c8b8"/>
    </svg>`;
    return `<div class="prod-card">
      <div class="prod-image" style="background:${colors[p.source]}">
        <div class="prod-img-bg" style="display:flex;align-items:center;justify-content:center;width:100%;height:100%">${svgBottle}</div>
        <div class="prod-badges">
          <span class="badge-dcto badge">-${dcto}% retail</span>
          <span class="badge-source badge badge-${p.source}">${p.source==='silk'?'SILK':'ELITE'}</span>
        </div>
      </div>
      <div class="prod-body">
        <p class="prod-brand">${p.brand}</p>
        <h3 class="prod-name">${p.name}</h3>
        <p class="prod-ml">${p.ml} · ${p.type} · ${p.notes}</p>
        <div class="prod-prices">
          <span class="prod-price-original">$${p.retail.toLocaleString('es-CL')}</span>
          <span class="prod-price-source">→ $${p.sourcePrice.toLocaleString('es-CL')}</span>
        </div>
        <div style="display:flex;align-items:baseline;gap:8px;margin-bottom:6px">
          <span style="font-size:.6rem;letter-spacing:.2em;text-transform:uppercase;color:var(--subtle)">Nuestro precio:</span>
          <span class="prod-price-our">$${p.ourPrice.toLocaleString('es-CL')}</span>
        </div>
        <p class="prod-margin-note">✓ Cliente ahorra $${savingsClient.toLocaleString('es-CL')} vs retail</p>
        <div class="prod-actions">
          <button class="btn-cart" onclick="addToCart(${p.id})">+ Agregar</button>
          <button class="btn-buy" onclick="buyNow(${p.id})">Comprar ya</button>
        </div>
      </div>
    </div>`;
  }).join('');
}

function filterProducts(gender, btn) {
  activeFilter = gender;
  document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  renderProducts();
}
function filterSource(val) { activeSource = val; renderProducts(); }
function searchProducts(val) { searchQuery = val; renderProducts(); }

// ════════════════════════════════════
//  CART
// ════════════════════════════════════
function addToCart(id) {
  const p = PRODUCTS.find(x=>x.id===id);
  const existing = cart.find(x=>x.id===id);
  if(existing) existing.qty++;
  else cart.push({...p, qty:1});
  updateCartUI();
  showToast(`✓ ${p.name} agregado al carrito`);
}

function buyNow(id) {
  addToCart(id);
  toggleCart();
}

function removeFromCart(id) {
  cart = cart.filter(x=>x.id!==id);
  updateCartUI();
}

function toggleCart() {
  document.getElementById('cartOverlay').classList.toggle('open');
  document.getElementById('cartPanel').classList.toggle('open');
}

function updateCartUI() {
  const count = cart.reduce((s,x)=>s+x.qty,0);
  document.getElementById('cartCount').textContent = count;
  const container = document.getElementById('cartItems');
  const footer = document.getElementById('cartFooter');
  if(cart.length===0){
    container.innerHTML='<div class="cart-empty"><div class="cart-empty-icon">🛍</div><p>Tu carrito está vacío</p></div>';
    footer.style.display='none'; return;
  }
  container.innerHTML = cart.map(p=>`
    <div class="cart-item">
      <div class="cart-item-img">🧴</div>
      <div class="cart-item-info">
        <div class="cart-item-name">${p.name}</div>
        <div class="cart-item-sub">${p.brand} · ${p.ml} · ${p.source==='silk'?'Silk':'Elite'}</div>
        <div class="cart-item-price">$${(p.ourPrice*p.qty).toLocaleString('es-CL')}</div>
      </div>
      <div>
        <span style="font-size:.75rem;color:var(--subtle)">×${p.qty}</span>
        <button class="cart-item-remove" onclick="removeFromCart(${p.id})">✕</button>
      </div>
    </div>`).join('');
  footer.style.display='block';
  const total = cart.reduce((s,x)=>s+x.ourPrice*x.qty,0);
  const savings = cart.reduce((s,x)=>s+(x.retail-x.ourPrice)*x.qty,0);
  document.getElementById('cartTotal').textContent='$'+total.toLocaleString('es-CL');
  document.getElementById('cartSavings').textContent='$'+savings.toLocaleString('es-CL');
}

// ════════════════════════════════════
//  CHECKOUT
// ════════════════════════════════════
function openCheckout() {
  if(cart.length===0){ showToast('Tu carrito está vacío'); return; }
  toggleCart();
  currentStep=1;
  document.getElementById('checkoutModal').classList.add('open');
  updateStepUI(1);
}
function closeCheckout() {
  document.getElementById('checkoutModal').classList.remove('open');
}
function selectSource(src, el) {
  selectedSource = src;
  document.querySelectorAll('.source-option').forEach(e=>e.classList.remove('selected'));
  el.classList.add('selected');
}
function formatCard(input) {
  let v = input.value.replace(/\D/g,'').substring(0,16);
  input.value = v.replace(/(.{4})/g,'$1 ').trim();
}
function nextStep(step) {
  if(step===2){
    const name=document.getElementById('shipName').value;
    const email=document.getElementById('shipEmail').value;
    const addr=document.getElementById('shipAddress').value;
    if(!name||!email||!addr){ showToast('Por favor completa todos los campos requeridos'); return; }
    const total=cart.reduce((s,x)=>s+x.ourPrice*x.qty,0);
    document.getElementById('s2Subtotal').textContent='$'+total.toLocaleString('es-CL');
    document.getElementById('s2Total').textContent='$'+total.toLocaleString('es-CL');
  }
  if(step===3){
    // Process order
    const orderId = 'VLR-'+Math.floor(10000+Math.random()*90000);
    document.getElementById('confirmOrderId').textContent=orderId;
    document.getElementById('flowProvider').textContent=selectedSource==='silk'?'Silk Perfumes':'Elite Perfumes';
    const name=document.getElementById('shipName').value+' '+document.getElementById('shipLastname').value;
    const total=cart.reduce((s,x)=>s+x.ourPrice*x.qty,0);
    const profit=cart.reduce((s,x)=>s+(x.ourPrice-x.sourcePrice)*x.qty,0);
    orders.push({
      id:orderId, client:name, 
      product:cart.map(x=>x.name).join(', '),
      provider:selectedSource==='silk'?'Silk Perfumes':'Elite Perfumes',
      sale:total, profit:profit,
      status:'processing',
      date:new Date().toLocaleDateString('es-CL')
    });
  }
  currentStep=step;
  updateStepUI(step);
}
function updateStepUI(step) {
  ['checkoutStep1','checkoutStep2','checkoutStep3'].forEach((s,i)=>{
    document.getElementById(s).style.display=i+1===step?'block':'none';
  });
  document.getElementById('stepLabel').textContent=`Paso ${step} de 3`;
  const titles=['Datos de Envío','Método de Pago','Orden Confirmada'];
  document.getElementById('stepTitle').textContent=titles[step-1];
  ['dot1','dot2','dot3'].forEach((d,i)=>{
    document.getElementById(d).classList.toggle('done', i<step);
  });
}
function finishOrder() {
  cart=[];
  updateCartUI();
  closeCheckout();
  showToast('🎉 ¡Gracias por tu compra! Revisa tu email.');
  currentStep=1;
}

// ════════════════════════════════════
//  COMPLAINTS
// ════════════════════════════════════
function submitComplaint() {
  const name=document.getElementById('cName').value;
  const order=document.getElementById('cOrder').value;
  const type=document.getElementById('cType').value;
  const desc=document.getElementById('cDesc').value;
  const provider=document.getElementById('cProvider').value;
  if(!name||!order||!desc){ showToast('Completa todos los campos del reclamo'); return; }
  const id='RCL-'+Math.floor(1000+Math.random()*9000);
  complaints.push({id,name,order,type,desc,provider,status:'open',date:new Date().toLocaleDateString('es-CL')});
  document.getElementById('cName').value='';
  document.getElementById('cOrder').value='';
  document.getElementById('cDesc').value='';
  renderComplaints();
  showToast('✓ Reclamo '+id+' registrado exitosamente');
}
function renderComplaints() {
  const open=complaints.filter(c=>c.status==='open').length;
  const resolved=complaints.filter(c=>c.status==='resolved').length;
  document.getElementById('totalComplaints').textContent=complaints.length;
  document.getElementById('openComplaints').textContent=open;
  document.getElementById('resolvedComplaints').textContent=resolved;
  const list=document.getElementById('complaintsList');
  if(complaints.length===0){
    list.innerHTML='<div class="no-results"><div class="no-results-icon">📋</div><p>No hay reclamos registrados</p></div>';
    return;
  }
  const statusLabel={open:'Abierto',progress:'En Proceso',resolved:'Resuelto'};
  const statusClass={open:'status-open',progress:'status-progress',resolved:'status-resolved'};
  list.innerHTML=[...complaints].reverse().map(c=>`
    <div class="complaint-item" id="complaint-${c.id}">
      <div class="complaint-header">
        <span class="complaint-id">${c.id} · ${c.date}</span>
        <span class="complaint-status ${statusClass[c.status]}">${statusLabel[c.status]}</span>
      </div>
      <div class="complaint-name">${c.name} — Orden ${c.order}</div>
      <div class="complaint-desc"><strong>${c.type}</strong><br/>${c.desc}</div>
      <div class="complaint-meta">Proveedor: ${c.provider}</div>
      <div class="complaint-actions">
        ${c.status!=='resolved'?`<button class="btn-resolve" onclick="updateComplaint('${c.id}','resolved')">Marcar Resuelto</button>`:''}
        ${c.status==='open'?`<button class="btn-progress" onclick="updateComplaint('${c.id}','progress')">En Proceso</button>`:''}
      </div>
    </div>`).join('');
}
function updateComplaint(id, status) {
  const c = complaints.find(x=>x.id===id);
  if(c) c.status=status;
  renderComplaints();
  showToast('Estado actualizado: '+{open:'Abierto',progress:'En Proceso',resolved:'Resuelto'}[status]);
}

// ════════════════════════════════════
//  ADMIN
// ════════════════════════════════════
function renderAdmin() {
  const totalSales = orders.reduce((s,o)=>s+o.sale,0);
  const totalProfit = orders.reduce((s,o)=>s+o.profit,0);
  const silk = orders.filter(o=>o.provider==='Silk Perfumes').length;
  const elite = orders.filter(o=>o.provider==='Elite Perfumes').length;
  document.getElementById('adminStats').innerHTML=`
    <div class="admin-card"><div class="admin-card-val">${orders.length}</div><div class="admin-card-label">Órdenes totales</div><div class="admin-card-sub">Desde el inicio</div></div>
    <div class="admin-card"><div class="admin-card-val">$${totalSales.toLocaleString('es-CL')}</div><div class="admin-card-label">Ventas totales</div><div class="admin-card-sub">CLP acumulado</div></div>
    <div class="admin-card"><div class="admin-card-val" style="color:var(--green)">$${totalProfit.toLocaleString('es-CL')}</div><div class="admin-card-label">Ganancia neta</div><div class="admin-card-sub">Margen acumulado</div></div>
    <div class="admin-card"><div class="admin-card-val">${silk}</div><div class="admin-card-label">Silk Perfumes</div><div class="admin-card-sub">Órdenes en este proveedor</div></div>
    <div class="admin-card"><div class="admin-card-val">${elite}</div><div class="admin-card-label">Elite Perfumes</div><div class="admin-card-sub">Órdenes en este proveedor</div></div>
    <div class="admin-card"><div class="admin-card-val">${complaints.filter(c=>c.status==='open').length}</div><div class="admin-card-label">Reclamos abiertos</div><div class="admin-card-sub">Requieren atención</div></div>`;
  const body = document.getElementById('ordersBody');
  const emptyMsg = document.getElementById('emptyOrders');
  if(orders.length===0){emptyMsg.style.display='block';body.innerHTML='';return;}
  emptyMsg.style.display='none';
  const statusMap={pending:'os-pending',processing:'os-processing',shipped:'os-shipped',delivered:'os-delivered'};
  const statusLabel={pending:'Pendiente',processing:'Procesando',shipped:'Enviado',delivered:'Entregado'};
  body.innerHTML=[...orders].reverse().map(o=>`
    <tr>
      <td style="font-family:'Cinzel',serif;font-size:.7rem;color:var(--gold)">${o.id}</td>
      <td>${o.client}</td>
      <td>${o.product}</td>
      <td><span style="font-size:.65rem;letter-spacing:.1em">${o.provider}</span></td>
      <td>$${o.sale.toLocaleString('es-CL')}</td>
      <td><span class="profit-pill">+$${o.profit.toLocaleString('es-CL')}</span></td>
      <td><span class="order-status ${statusMap[o.status]}">${statusLabel[o.status]}</span></td>
    </tr>`).join('');
}

// ════════════════════════════════════
//  MARGIN CALCULATOR
// ════════════════════════════════════
function calcMargin() {
  const retail=parseFloat(document.getElementById('calcRetail').value)||0;
  const source=parseFloat(document.getElementById('calcSource').value)||0;
  const sale=parseFloat(document.getElementById('calcSale').value)||0;
  if(!retail||!source||!sale){document.getElementById('calcResult').style.display='none';return;}
  document.getElementById('calcResult').style.display='block';
  const margin=sale-source;
  const dcto=Math.round((1-sale/retail)*100);
  const statusEl=document.getElementById('rStatus');
  let status='';
  if(margin>=10000&&margin<=15000&&sale<retail){status='✅ Perfecto — dentro del rango VELOUR';statusEl.style.color='#27ae60';}
  else if(margin<10000){status='⚠️ Margen bajo — sube al menos $'+(10000-margin).toLocaleString('es-CL');statusEl.style.color='#e67e22';}
  else if(margin>15000){status='⚠️ Margen alto — considera bajar $'+(margin-15000).toLocaleString('es-CL');statusEl.style.color='#e67e22';}
  else if(sale>=retail){status='🚫 Tu precio es igual o mayor al retail';statusEl.style.color='#c0392b';}
  document.getElementById('rRetail').textContent='$'+retail.toLocaleString('es-CL');
  document.getElementById('rSource').textContent='$'+source.toLocaleString('es-CL');
  document.getElementById('rSale').textContent='$'+sale.toLocaleString('es-CL');
  document.getElementById('rMargin').textContent='$'+margin.toLocaleString('es-CL');
  document.getElementById('rDcto').textContent=dcto+'% menos que retail';
  statusEl.textContent=status;
}
function renderExamples() {
  const examples=[
    {prod:'Good Girl 80ml',retail:89990,source:22990,our:34990},
    {prod:'1 Million 100ml',retail:79990,source:19990,our:32990},
    {prod:'Asad Zanzibar 100ml',retail:39990,source:15990,our:27990},
    {prod:'CK One 200ml',retail:49990,source:12990,our:24990},
  ];
  document.getElementById('examplesList').innerHTML=examples.map(e=>`
    <div style="padding:14px;border:1px solid var(--line);font-size:.75rem">
      <div style="font-weight:500;margin-bottom:6px;color:var(--dark)">${e.prod}</div>
      <div style="display:flex;justify-content:space-between;color:var(--subtle)"><span>Retail:</span><span style="text-decoration:line-through">$${e.retail.toLocaleString('es-CL')}</span></div>
      <div style="display:flex;justify-content:space-between;color:var(--subtle)"><span>Proveedor:</span><span>$${e.source.toLocaleString('es-CL')}</span></div>
      <div style="display:flex;justify-content:space-between;color:var(--gold);font-weight:500"><span>Nuestro precio:</span><span>$${e.our.toLocaleString('es-CL')}</span></div>
      <div style="display:flex;justify-content:space-between;color:var(--green);margin-top:4px"><span>Ganancia:</span><span>+$${(e.our-e.source).toLocaleString('es-CL')}</span></div>
    </div>`).join('');
}

// ════════════════════════════════════
//  TOAST
// ════════════════════════════════════
function showToast(msg) {
  const t=document.getElementById('toast');
  t.textContent=msg; t.classList.add('show');
  setTimeout(()=>t.classList.remove('show'),3000);
}

// ════════════════════════════════════
//  INIT
// ════════════════════════════════════
renderProducts();
</script>
</body>
</html>
