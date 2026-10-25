<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CHAPCHAP SYSTEM COMPLET</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:system-ui}
body{max-width:400px;margin:0 auto;background:#0f0f0f;min-height:100vh}
.page{display:none;min-height:100vh}.page.active{display:block}
.top{padding:14px;display:flex;align-items:center;gap:10px;font-weight:800;color:#fff}
.btn{width:calc(100% - 32px);margin:16px;background:#FF6B00;color:#fff;border:none;padding:16px;border-radius:12px;font-weight:900;font-size:15px;cursor:pointer}
.card{background:#fff;border-radius:16px;margin:12px 16px;padding:14px}
.dark{background:#1a1a1a;color:#fff;border-radius:16px;margin:12px 16px;padding:16px;border:1px solid #333}
.green{background:#052e1a;border:1px solid #16a34a;color:#4ade80;border-radius:12px;padding:12px;margin-top:10px}
.orangeTag{background:#FF6B00;color:#fff;padding:4px 10px;border-radius:20px;font-size:11px;font-weight:700}
.input{width:100%;padding:14px;border:1px solid #333;border-radius:12px;background:#222;color:#fff;margin-top:10px}
</style>
</head>
<body>

<!-- LOGIN SELECTOR -->
<div id="login" class="page active" style="background:#fff;display:flex;flex-direction:column;justify-content:center;padding:20px">
<h1 style="color:#FF6B00;text-align:center">🏠 CHAPCHAP</h1>
<p style="text-align:center;opacity:.6;margin-top:6px">Choisis ton accès</p>
<button class="btn" onclick="openPage('client')">👤 Je suis CLIENT - Louer studio</button>
<button class="btn" style="background:#101828" onclick="openPage('proprio')">🏠 Je suis PROPRIO - Mon appart</button>
<button class="btn" style="background:#000;border:1px dashed #FF6B00" onclick="document.getElementById('adminLogin').style.display='flex'">🔒 ADMIN SECRET - Voir marge</button>
<div id="adminLogin" style="display:none;position:fixed;inset:0;background:rgba(0,0,0,.8);align-items:center;justify-content:center;padding:20px">
<div style="background:#1a1a1a;padding:20px;border-radius:16px;width:100%;max-width:360px">
<h3 style="color:#fff">🔒 Admin Login</h3>
<input id="pass" class="input" type="password" placeholder="Mot de passe admin">
<button class="btn" style="width:100%" onclick="if(document.getElementById('pass').value=='chap2024'){openPage('admin');document.getElementById('adminLogin').style.display='none'}else{alert('Faux code')}">Entrer</button>
</div>
</div>
</div>

<!-- 1. CLIENT - VOIT 12000F SEULEMENT -->
<div id="client" class="page" style="background:#fff">
<div class="top" style="background:#FF6B00"><span onclick="openPage('login')">←</span> Studios à Abidjan</div>
<div style="height:160px;background:url('https://images.unsplash.com/photo-1522708323590-d24dbb6b0267?w=600') center/cover"></div>
<div style="padding:16px">
<h2>Studio moderne - Cocody Riviera</h2>
<p style="margin-top:4px">⭐ 4.7 • 12 avis • 📍 Cocody, Abidjan</p>
<div style="margin-top:10px"><span class="orangeTag">WiFi</span> <span class="orangeTag" style="background:#f1f5f9;color:#000">Climatisé</span> <span class="orangeTag" style="background:#f1f5f9;color:#000">Sécurisé</span></div>
<h2 style="color:#FF6B00;margin-top:14px">12 000F / nuit</h2>
<p style="font-size:11px;opacity:.5;margin-top:2px">Prix final. Aucune commission affichée.</p>
<p style="font-size:13px;margin-top:12px;line-height:20px">Studio propre, clim, cuisine équipée, sécurité 24/7. Proche route principale. Idéal court séjour.</p>
</div>
<button class="btn" onclick="openPage('clientConfirm')">Réserver</button>
</div>

<div id="clientConfirm" class="page" style="background:#fff">
<div class="top" style="background:#fff;color:#000;border-bottom:1px solid #eee"><span onclick="openPage('client')">←</span> Confirmation</div>
<div style="padding:16px">
<div style="background:#FFF7ED;border-radius:16px;padding:16px">
<b>Résumé</b><br><br>
📅 15 - 17 déc • 2 nuits<br>
🏠 Studio Cocody Riviera<br>
👥 2 voyageurs<br><br>
<div style="display:flex;justify-content:space-between;border-top:1px dashed #FF6B00;padding-top:10px"><b>Total à payer</b><b style="color:#FF6B00">24 000F</b></div>
<p style="font-size:10px;opacity:.5;margin-top:6px">Tu payes 24 000F. C'est tout.</p>
</div>
<p style="margin-top:16px;font-weight:700">Payer avec</p>
<div style="display:flex;gap:8px;margin-top:8px"><div class="card" style="flex:1;text-align:center;border-color:#FF6B00;margin:0">Wave</div><div class="card" style="flex:1;text-align:center;margin:0">OM</div><div class="card" style="flex:1;text-align:center;margin:0">MTN</div></div>
<button class="btn" onclick="alert('✅ Réservation confirmée ! Proprio notifié.')">Confirmer et payer 24 000F</button>
</div>
</div>

<!-- 2. PROPRIO - VOIT 20400F SEULEMENT -->
<div id="proprio" class="page" style="background:#f8fafc">
<div class="top" style="background:#101828"><span onclick="openPage('login')">←</span> Tableau de bord Propriétaire</div>
<div style="padding:16px">
<div class="card" style="border-left:4px solid #16a34a">
<p style="font-size:12px;color:#16a34a;font-weight:700">✅ Réservation confirmée #2248</p>
<b style="display:block;margin-top:8px">Studio Cocody - 15-16 Déc</b>
<p style="font-size:12px;opacity:.6">1 nuit • 1 invité • Koffi (4.9 ⭐)</p>
<div style="margin-top:12px;background:#f0fdf4;border-radius:12px;padding:12px">
<p style="font-size:12px;opacity:.7">Vous recevez</p>
<p style="font-size:28px;font-weight:900;color:#16a34a">20 400F</p>
<p style="font-size:11px;opacity:.6">Virement prévu: 16 Déc • 24-48h<br>Paiement reçu via CHAPCHAP - Sécurisé</p>
</div>
<p style="font-size:10px;opacity:.4;margin-top:8px">Le client a payé sur CHAPCHAP. Tu reçois ton argent, c'est tout.</p>
</div>
<div class="card">
<b>Vos gains ce mois</b>
<p style="font-size:24px;font-weight:900;margin-top:6px">340 000F</p>
<p style="font-size:11px;opacity:.6">3 logements actifs • Taux occupation 78%</p>
</div>
</div>
</div>

<!-- 3. ADMIN SECRET - VOIT TOUT + MARGE 3600F -->
<div id="admin" class="page" style="background:#0f0f0f">
<div class="top" style="background:#000;border-bottom:1px solid #333"><span onclick="openPage('login')">←</span> 🔒 ADMIN CHAPCHAP - CONFIDENTIEL</div>
<div style="padding:16px">
<div class="dark">
<p style="font-size:10px;color:#FF6B00;letter-spacing:2px">🔒 ACCÈS RESTREINT - CONFIDENTIEL</p>
<h2 style="margin-top:8px">Transaction #2248 - Detail complet</h2>
<p style="font-size:11px;opacity:.5;margin-top:4px">24 Oct 2024 • 14:32 • Completed</p>

<div style="margin-top:16px;border-top:1px solid #333;padding-top:12px">
<p style="font-size:12px;opacity:.6">Répartition du paiement</p>
<div style="display:flex;justify-content:space-between;margin-top:10px"><span>Client a payé</span><b>24 000F</b></div>
<div style="display:flex;justify-content:space-between;margin-top:6px"><span>Propriétaire reçoit</span><b>20 400F</b></div>
</div>

<div class="green">
<div style="display:flex;justify-content:space-between;align-items:center">
<div><p style="font-size:11px;opacity:.8">🔒 MARGE CACHÉE CHAPCHAP</p><p style="font-size:10px">Commission plateforme</p></div>
<div style="text-align:right"><p style="font-size:20px;font-weight:900">3 600F</p><p style="font-size:12px">15%</p></div>
</div>
<p style="font-size:10px;margin-top:8px;opacity:.7">Cette vue est confidentielle. Non visible Client ni Propriétaire.</p>
</div>

<div style="margin-top:16px;background:#1a1a1a;border-radius:12px;padding:12px">
<p style="font-size:12px">💳 Wave transaction TXN: WV-78492310 • Success</p>
<p style="font-size:11px;opacity:.5;margin-top:6px">Client: Koffi • Proprio: Aïssata • Logement: Studio Cocody</p>
</div>

<div class="dark" style="margin-top:16px">
<h3>Vue d'ensemble business</h3>
<div style="display:flex;gap:12px;margin-top:10px">
<div><p style="font-size:11px;opacity:.6">Total réservations</p><b style="font-size:20px">156</b></div>
<div><p style="font-size:11px;opacity:.6">Revenue total</p><b style="font-size:20px">5.2M F</b></div>
<div><p style="font-size:11px;opacity:.6">Hidden margin</p><b style="font-size:20px;color:#4ade80">780 000F</b></div>
</div>
</div>
</div>
</div>

<script>
function openPage(id){document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));document.getElementById(id).classList.add('active');window.scrollTo(0,0)}
</script>
</body>
</html>
