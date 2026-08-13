<!doctype html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hospital Dr. Salvador Paredes — Archivo de Personal</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;600;700&family=Inter:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500;600&display=swap');

:root{
  --paper:#ECF1F6;
  --paper-alt:#E1E8F0;
  --card:#F5F8FB;
  --ink:#16222E;
  --ink-soft:#4C5C6C;
  --ink-faint:#8A99A8;
  --accent:#2C5F8A;
  --accent-dark:#1B3E5C;
  --accent-soft:#DAE6F0;
  --amber:#A8781F;
  --amber-soft:#F1E4C8;
  --red:#A0402A;
  --red-soft:#F1DAD1;
  --blue:#3E7C93;
  --blue-soft:#DCEAEF;
  --line:#C4CFDB;
  --line-soft:#DCE4EC;
  --sidebar:#0F1D2E;
  --sidebar-line:#203044;
  --sidebar-ink:#DCE6F0;
  --sidebar-ink-dim:#7E93A8;
  --font-display:'Space Grotesk',Arial,sans-serif;
  --font-body:'Inter',Arial,sans-serif;
  --font-mono:'IBM Plex Mono','Courier New',monospace;
  --radius:3px;
}

*{box-sizing:border-box;}
html,body{margin:0;padding:0;}
body{
  background:var(--paper);
  color:var(--ink);
  font-family:var(--font-body);
  font-size:14px;
  line-height:1.45;
  -webkit-font-smoothing:antialiased;
}
button{font-family:inherit;cursor:pointer;}
input,select,textarea{font-family:inherit;font-size:14px;}
::selection{background:var(--accent-soft);}
a{color:var(--accent-dark);}

@media (prefers-reduced-motion: reduce){
  *{animation-duration:0.001ms !important; transition-duration:0.001ms !important;}
}

:focus-visible{
  outline:2px solid var(--accent-dark);
  outline-offset:2px;
}

/* ---------- shell ---------- */
#app{display:flex; min-height:100vh;}

.sidebar{
  width:236px;
  flex-shrink:0;
  background:var(--sidebar);
  color:var(--sidebar-ink);
  display:flex;
  flex-direction:column;
  position:sticky;
  top:0;
  height:100vh;
}
.sidebar-brand{
  padding:26px 22px 18px 22px;
  border-bottom:1px solid var(--sidebar-line);
}
.sidebar-brand .mark{
  font-family:var(--font-mono);
  font-size:11px;
  letter-spacing:.14em;
  color:var(--sidebar-ink-dim);
  text-transform:uppercase;
}
.sidebar-brand h1{
  font-family:var(--font-display);
  font-size:19px;
  font-weight:600;
  margin:6px 0 0 0;
  letter-spacing:-0.01em;
}
.sidebar-nav{
  flex:1;
  padding:18px 0 18px 0;
}
.nav-item{
  display:flex;
  align-items:center;
  gap:10px;
  padding:11px 20px 11px 22px;
  margin:2px 0 2px 14px;
  border-radius:3px 0 0 3px;
  color:var(--sidebar-ink-dim);
  font-size:13.5px;
  font-weight:500;
  cursor:pointer;
  border:1px solid transparent;
  border-right:none;
  position:relative;
}
.nav-item svg{width:16px;height:16px;flex-shrink:0;opacity:.85;}
.nav-item:hover{color:var(--sidebar-ink); background:rgba(255,255,255,0.04);}
.nav-item.active{
  background:var(--paper);
  color:var(--ink);
  margin-right:-1px;
}
.nav-item.active svg{opacity:1;}
.nav-count{
  margin-left:auto;
  font-family:var(--font-mono);
  font-size:11px;
  color:inherit;
  opacity:.7;
}
.sidebar-foot{
  padding:16px 22px 22px 22px;
  border-top:1px solid var(--sidebar-line);
  font-family:var(--font-mono);
  font-size:11.5px;
  color:var(--sidebar-ink-dim);
}
.sidebar-foot .clock{color:var(--sidebar-ink); font-size:15px; margin-bottom:2px; letter-spacing:.02em;}

.main{
  flex:1;
  min-width:0;
  padding:30px 40px 60px 40px;
  max-width:1180px;
}
.topbar{
  display:flex;
  align-items:flex-end;
  justify-content:space-between;
  margin-bottom:26px;
  gap:16px;
  flex-wrap:wrap;
}
.topbar .eyebrow{
  font-family:var(--font-mono);
  font-size:11px;
  letter-spacing:.12em;
  text-transform:uppercase;
  color:var(--ink-faint);
  margin:0 0 4px 0;
}
.topbar h2{
  font-family:var(--font-display);
  font-size:26px;
  font-weight:600;
  margin:0;
  letter-spacing:-0.01em;
}
.topbar-actions{display:flex; gap:10px; flex-wrap:wrap;}

.btn{
  border:1px solid var(--ink);
  background:transparent;
  color:var(--ink);
  padding:9px 16px;
  border-radius:var(--radius);
  font-size:13px;
  font-weight:500;
  display:inline-flex;
  align-items:center;
  gap:7px;
}
.btn:hover{background:var(--ink); color:var(--paper);}
.btn-primary{
  background:var(--accent-dark);
  border-color:var(--accent-dark);
  color:#fff;
}
.btn-primary:hover{background:var(--accent);}
.btn-danger{border-color:var(--red); color:var(--red);}
.btn-danger:hover{background:var(--red); color:#fff;}
.btn-ghost{border-color:transparent; padding:9px 10px;}
.btn-ghost:hover{background:var(--paper-alt); color:var(--ink);}
.btn-sm{padding:5px 11px; font-size:12px;}

/* ---------- cards / grid ---------- */
.grid{display:grid; gap:16px;}
.grid-4{grid-template-columns:repeat(4,1fr);}
.grid-2{grid-template-columns:1.4fr 1fr;}
@media (max-width:900px){ .grid-4{grid-template-columns:repeat(2,1fr);} .grid-2{grid-template-columns:1fr;} }

.card{
  background:var(--card);
  border:1px solid var(--line);
  border-radius:var(--radius);
  padding:18px 18px 16px 18px;
}
.card h3{
  font-family:var(--font-display);
  font-size:14.5px;
  font-weight:600;
  margin:0 0 12px 0;
}
.kpi{padding:16px 18px;}
.kpi .label{
  font-family:var(--font-mono);
  font-size:10.5px;
  letter-spacing:.08em;
  text-transform:uppercase;
  color:var(--ink-faint);
  margin-bottom:8px;
}
.kpi .value{
  font-family:var(--font-mono);
  font-size:32px;
  font-weight:600;
  line-height:1;
}
.kpi .sub{font-size:12px; color:var(--ink-soft); margin-top:6px;}
.kpi.accent .value{color:var(--accent-dark);}
.kpi.amber .value{color:var(--amber);}
.kpi.red .value{color:var(--red);}

/* bars */
.bar-row{display:flex; align-items:center; gap:10px; margin-bottom:9px;}
.bar-row .bar-label{width:150px; font-size:12px; color:var(--ink-soft); flex-shrink:0;}
.bar-track{flex:1; height:9px; background:var(--paper-alt); border-radius:2px; overflow:hidden;}
.bar-fill{height:100%; background:var(--accent); border-radius:2px;}
.bar-row .bar-val{width:34px; text-align:right; font-family:var(--font-mono); font-size:12px; color:var(--ink-soft);}

/* alerts */
.alert-item{
  display:flex; justify-content:space-between; align-items:center;
  padding:9px 0; border-bottom:1px solid var(--line-soft);
  font-size:13px;
}
.alert-item:last-child{border-bottom:none;}
.alert-tag{
  font-family:var(--font-mono); font-size:10.5px; padding:2px 7px;
  border-radius:2px; text-transform:uppercase; letter-spacing:.04em;
}
.tag-amber{background:var(--amber-soft); color:var(--amber);}
.tag-red{background:var(--red-soft); color:var(--red);}
.empty-note{color:var(--ink-faint); font-size:13px; padding:6px 0;}

/* ---------- tables ---------- */
.table-wrap{overflow-x:auto;}
table{width:100%; border-collapse:collapse; font-size:13px;}
thead th{
  text-align:left; font-family:var(--font-mono); font-weight:500; font-size:10.5px;
  text-transform:uppercase; letter-spacing:.06em; color:var(--ink-faint);
  padding:0 12px 10px 12px; border-bottom:1px solid var(--ink);
  white-space:nowrap;
}
tbody td{padding:11px 12px; border-bottom:1px solid var(--line-soft); vertical-align:middle;}
tbody tr:hover{background:var(--paper-alt);}
td.mono, .mono{font-family:var(--font-mono);}
td.num{text-align:right; font-family:var(--font-mono);}

.stamp{
  display:inline-block;
  font-family:var(--font-mono);
  font-size:10.5px;
  font-weight:600;
  letter-spacing:.06em;
  text-transform:uppercase;
  padding:3px 9px;
  border-radius:2px;
  border:1.5px solid currentColor;
  transform:rotate(-2deg);
}
.stamp-activo{color:var(--accent-dark); background:var(--accent-soft);}
.stamp-licencia{color:var(--amber); background:var(--amber-soft);}
.stamp-interinato{color:var(--blue); background:var(--blue-soft);}
.stamp-baja{color:var(--red); background:var(--red-soft);}

.toolbar{display:flex; gap:10px; align-items:center; margin-bottom:16px; flex-wrap:wrap;}
.toolbar input[type=text], .toolbar select, .field select, .field input, .field textarea{
  padding:8px 11px; border:1px solid var(--line); border-radius:var(--radius);
  background:#fff; color:var(--ink); min-width:0;
}
.toolbar input[type=text]{min-width:220px;}
.spacer{flex:1;}

/* ---------- ficha (signature element) ---------- */
.ficha{
  background:var(--card);
  border:1.5px solid var(--ink);
  border-radius:var(--radius);
  position:relative;
  padding:22px 24px 20px 34px;
  margin-bottom:18px;
}
.ficha::before{
  content:'';
  position:absolute; left:10px; top:14px; bottom:14px; width:1px;
  background-image:linear-gradient(var(--ink-faint) 40%, transparent 0%);
  background-size:1px 8px;
  opacity:.35;
}
.ficha-top{display:flex; justify-content:space-between; align-items:flex-start; gap:14px; margin-bottom:14px; flex-wrap:wrap;}
.ficha-exp{font-family:var(--font-mono); font-size:11px; color:var(--ink-faint); letter-spacing:.06em;}
.ficha-name{font-family:var(--font-display); font-size:20px; font-weight:600; margin:2px 0 0 0;}
.ficha-meta{font-size:12.5px; color:var(--ink-soft); margin-top:3px;}
.ficha-grid{display:grid; grid-template-columns:repeat(4,1fr); gap:14px; margin:16px 0;}
@media (max-width:780px){.ficha-grid{grid-template-columns:repeat(2,1fr);}}
.ficha-stat .label{font-family:var(--font-mono); font-size:10px; text-transform:uppercase; letter-spacing:.06em; color:var(--ink-faint); margin-bottom:4px;}
.ficha-stat .val{font-family:var(--font-mono); font-size:20px; font-weight:600;}
.ficha-stat .val.deficit{color:var(--red);}
.ficha-actions{display:flex; gap:8px; flex-wrap:wrap; margin-top:14px; padding-top:14px; border-top:1px solid var(--line-soft);}

/* ---------- modal ---------- */
.overlay{
  position:fixed; inset:0; background:rgba(22,33,31,0.42);
  display:none; align-items:flex-start; justify-content:center;
  padding:44px 20px; overflow-y:auto; z-index:50;
}
.overlay.open{display:flex;}
.modal{
  background:var(--card); border:1px solid var(--ink); border-radius:var(--radius);
  width:100%; max-width:560px; padding:26px 28px 24px 28px;
}
.modal h3{font-family:var(--font-display); font-size:18px; margin:0 0 18px 0;}
.field{margin-bottom:14px;}
.field label{display:block; font-size:12px; font-weight:500; color:var(--ink-soft); margin-bottom:5px;}
.field input, .field select, .field textarea{width:100%;}
.field-row{display:grid; grid-template-columns:1fr 1fr; gap:12px;}
.field-note{font-size:11.5px; color:var(--ink-faint); margin-top:4px;}
.autocomplete-list{
  position:absolute; top:100%; left:0; right:0; z-index:10;
  background:#fff; border:1px solid var(--ink); border-top:none;
  max-height:220px; overflow-y:auto; border-radius:0 0 var(--radius) var(--radius);
}
.autocomplete-item{padding:9px 12px; font-size:13px; cursor:pointer; border-bottom:1px solid var(--line-soft);}
.autocomplete-item:last-child{border-bottom:none;}
.autocomplete-item:hover{background:var(--accent-soft);}
.autocomplete-empty{padding:9px 12px; font-size:12.5px; color:var(--ink-faint);}
.modal-actions{display:flex; justify-content:flex-end; gap:10px; margin-top:20px; padding-top:16px; border-top:1px solid var(--line-soft);}

/* ---------- indicators ---------- */
.indicator-card{
  background:var(--card); border:1px solid var(--line); border-radius:var(--radius);
  padding:14px 16px; display:flex; justify-content:space-between; align-items:center; gap:10px;
}
.indicator-card .txt .name{font-weight:500; font-size:13.5px;}
.indicator-card .txt .note{font-size:11.5px; color:var(--ink-faint); margin-top:2px;}
.indicator-card .value{font-family:var(--font-mono); font-size:22px; font-weight:600; color:var(--accent-dark); white-space:nowrap;}

.section-title{font-family:var(--font-display); font-size:15px; font-weight:600; margin:28px 0 12px 0;}
.section-title:first-child{margin-top:0;}

.loading-screen{
  position:fixed; inset:0; background:var(--paper); display:flex; align-items:center; justify-content:center;
  flex-direction:column; gap:10px; z-index:100; font-family:var(--font-mono); color:var(--ink-soft); font-size:13px;
}

/* ---------- login ---------- */
.login-screen{
  position:fixed; inset:0; background:var(--sidebar); display:flex; align-items:center; justify-content:center; z-index:200;
}
.login-box{
  width:100%; max-width:340px; background:var(--paper); border:1px solid var(--line); border-radius:var(--radius);
  padding:30px 28px 26px 28px;
}
.login-box .mark{
  font-family:var(--font-mono); font-size:11px; letter-spacing:.14em; color:var(--ink-faint); text-transform:uppercase;
}
.login-box h1{
  font-family:var(--font-display); font-size:20px; font-weight:600; margin:6px 0 20px 0; letter-spacing:-0.01em;
}
.login-box .field{margin-bottom:14px;}
.login-box .field label{display:block; font-size:12.5px; font-weight:500; color:var(--ink-soft); margin-bottom:5px;}
.login-box .field input{
  width:100%; padding:9px 11px; border:1px solid var(--line); border-radius:var(--radius); background:#fff; color:var(--ink);
}
.login-box .field input:focus{outline:2px solid var(--accent-dark); outline-offset:1px;}
.login-error{
  background:var(--red-soft); color:var(--red); border-radius:var(--radius); padding:8px 10px; font-size:12.5px; margin-bottom:14px; display:none;
}
.login-box button[type="submit"]{width:100%; justify-content:center; margin-top:4px;}
.btn-logout{
  margin-top:10px; font-family:var(--font-mono); font-size:11px; color:var(--sidebar-ink-dim); background:none; border:none;
  cursor:pointer; padding:0; text-decoration:underline;
}
.btn-logout:hover{color:var(--sidebar-ink);}
</style>
</head>
<body>

<div class="login-screen" id="loginScreen" style="display:none;">
  <div class="login-box">
    <div class="mark">Hospital Dr. Salvador Paredes</div>
    <h1>Acceso · RR. HH.</h1>
    <div class="login-error" id="loginError"></div>
    <form id="formLogin">
      <div class="field"><label>Correo electrónico</label><input required type="email" id="loginEmail" autocomplete="username"></div>
      <div class="field"><label>Contraseña</label><input required type="password" id="loginPassword" autocomplete="current-password"></div>
      <button type="submit" class="btn btn-primary">Iniciar sesión</button>
    </form>
  </div>
</div>

<div class="loading-screen" id="loadingScreen" style="display:none;">
  <div class="mono">CARGANDO ARCHIVO…</div>
</div>

<div id="app" style="display:none;">
  <nav class="sidebar">
    <div class="sidebar-brand">
      <div class="mark">Hospital Dr. Salvador Paredes</div>
      <h1>Archivo de<br>Personal</h1>
      <div class="mark" style="margin-top:6px;">RR. HH. · CONTROL INTERNO</div>
    </div>
    <div class="sidebar-nav" id="sidebarNav"></div>
    <div class="sidebar-foot">
      <div class="clock" id="clock">--:--</div>
      <div id="today">--</div>
      <button class="btn-logout" id="btnLogout">Cerrar sesión</button>
    </div>
  </nav>
  <main class="main" id="main"></main>
</div>

<div class="overlay" id="overlay">
  <div class="modal" id="modalBody"></div>
</div>

<script src="https://www.gstatic.com/firebasejs/10.13.1/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.13.1/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.13.1/firebase-firestore-compat.js"></script>
<script>
/* ======================= FIREBASE ======================= */
const firebaseConfig = {
  apiKey: "AIzaSyDYNYxxKXREvKUl0puhjQJf_VWGpLpIU9k",
  authDomain: "recursos-humanos-hsp.firebaseapp.com",
  projectId: "recursos-humanos-hsp",
  storageBucket: "recursos-humanos-hsp.firebasestorage.app",
  messagingSenderId: "293612494806",
  appId: "1:293612494806:web:d13a72ce3be38124dc4e77",
  measurementId: "G-TWDP41YHG3"
};
firebase.initializeApp(firebaseConfig);
const auth = firebase.auth();
const db = firebase.firestore();
const STATE_COLLECTION = 'hr_state';

/* ======================= ESTADO Y PERSISTENCIA ======================= */
const state = {
  page:'dashboard',
  employees:[],
  absences:[],
  indicators:[],
  expCounter:0,
  plantillaTotal:337,
  viewingFicha:null,
  filterEstado:'Todos',
  searchTerm:'',
  filterAusEmp:'Todos',
  filterAusTipo:'Todos'
};

const ABSENCE_TYPES = [
  'Permiso por día',
  'Vacaciones anuales',
  'Vacaciones profilácticas',
  'Permiso NO justificado',
  'Incapacidad médica',
  'Duelo',
  'Maternidad',
  'Permiso por horas'
];
const AUSENTISMO_TYPES = ['Permiso por día','Permiso NO justificado','Incapacidad médica','Duelo','Maternidad'];

async function safeGet(key){
  try{
    const doc = await db.collection(STATE_COLLECTION).doc(key).get();
    return doc.exists ? doc.data().value : null;
  }catch(e){ console.error('No se pudo leer', key, e); return null; }
}
async function saveKey(key,value){
  try{ await db.collection(STATE_COLLECTION).doc(key).set({value}); }
  catch(e){ console.error('No se pudo guardar', key, e); alert('No se pudo guardar el cambio. Revisa tu conexión e inténtalo de nuevo.'); }
}

async function loadAll(){
  const [emp,abs,ind,ctr,plant] = await Promise.all([
    safeGet('employees'), safeGet('absences'), safeGet('indicators'), safeGet('expCounter'), safeGet('plantillaTotal')
  ]);
  state.employees = emp || [];
  state.absences = abs || [];
  state.indicators = ind || [];
  state.expCounter = ctr || 0;
  state.plantillaTotal = plant || 337;
  document.getElementById('loadingScreen').style.display='none';
  document.getElementById('app').style.display='flex';
  renderAll();
}

/* ======================= SESIÓN ======================= */
function showLogin(){
  document.getElementById('loadingScreen').style.display='none';
  document.getElementById('app').style.display='none';
  document.getElementById('loginScreen').style.display='flex';
}
function showLoading(){
  document.getElementById('loginScreen').style.display='none';
  document.getElementById('app').style.display='none';
  document.getElementById('loadingScreen').style.display='flex';
}

document.getElementById('formLogin').addEventListener('submit', async ev=>{
  ev.preventDefault();
  const email = document.getElementById('loginEmail').value.trim();
  const password = document.getElementById('loginPassword').value;
  const errBox = document.getElementById('loginError');
  errBox.style.display='none';
  try{
    await auth.signInWithEmailAndPassword(email, password);
  }catch(e){
    errBox.textContent = 'Correo o contraseña incorrectos.';
    errBox.style.display='block';
  }
});

document.getElementById('btnLogout').addEventListener('click', async ()=>{
  await auth.signOut();
});

auth.onAuthStateChanged(user=>{
  if(user){
    showLoading();
    loadAll();
  } else {
    showLogin();
  }
});

/* ======================= UTILIDADES ======================= */
function uid(){ return Math.random().toString(36).slice(2,10)+Date.now().toString(36).slice(-4); }
function fmtDate(iso){
  if(!iso) return '—';
  const [y,m,d] = iso.split('-');
  return `${d}/${m}/${y}`;
}
function todayISO(){ return new Date().toISOString().slice(0,10); }
function daysBetween(a,b){ return Math.round((new Date(b)-new Date(a))/86400000)+1; }
function yearsCompleted(fechaIngreso, ref){
  const start = new Date(fechaIngreso), end = new Date(ref||todayISO());
  let years = end.getFullYear()-start.getFullYear();
  const anniv = new Date(start); anniv.setFullYear(start.getFullYear()+years);
  if(anniv>end) years--;
  return Math.max(0,years);
}
function vacScaleYear(n){ if(n>=4) return 20; if(n===3) return 15; if(n===2) return 12; if(n===1) return 10; return 0; }
function vacAccrued(fechaIngreso){
  const yrs = yearsCompleted(fechaIngreso);
  let total=0;
  for(let y=1;y<=yrs;y++) total += vacScaleYear(y);
  return total;
}
function antiguedadTxt(fechaIngreso){
  const start=new Date(fechaIngreso), end=new Date();
  let years=end.getFullYear()-start.getFullYear();
  let months=end.getMonth()-start.getMonth();
  if(end.getDate()<start.getDate()) months--;
  if(months<0){ years--; months+=12; }
  if(years<=0 && months<=0) return 'menos de 1 mes';
  let parts=[];
  if(years>0) parts.push(years+(years===1?' año':' años'));
  if(months>0) parts.push(months+(months===1?' mes':' meses'));
  return parts.join(', ');
}
function empAbsences(empId,tipo){
  return state.absences.filter(a=>a.employeeId===empId && (!tipo || a.tipo===tipo));
}
function sumDias(list){ return list.reduce((s,a)=>s+(a.dias||0),0); }
function saldoAnual(emp){
  const tomados = sumDias(empAbsences(emp.id,'Vacaciones anuales'));
  return vacAccrued(emp.fechaIngreso) - tomados + (emp.ajusteVacacional||0);
}
function saldoProfilactico(emp){
  const tomados = sumDias(empAbsences(emp.id,'Vacaciones profilácticas'));
  return (emp.diasProfilacticos||0) - tomados;
}
function activeEmployees(){ return state.employees.filter(e=>e.estado!=='Baja'); }
function expFmt(n){ return 'EXP-'+String(n).padStart(4,'0'); }

function isActiveToday(a){
  const t = todayISO();
  return a.fechaInicio<=t && a.fechaFin>=t;
}
function bucketFor(tipo){
  if(tipo==='Vacaciones anuales' || tipo==='Vacaciones profilácticas') return 'vacaciones';
  if(tipo==='Incapacidad médica') return 'incapacidades';
  return 'permisos';
}
function personasEnCadaBucket(){
  const buckets = { permisos:new Set(), vacaciones:new Set(), incapacidades:new Set() };
  state.absences.filter(isActiveToday).forEach(a=>{
    const emp = state.employees.find(e=>e.id===a.employeeId);
    if(!emp || emp.estado==='Baja') return;
    buckets[bucketFor(a.tipo)].add(a.employeeId);
  });
  return { permisos:buckets.permisos.size, vacaciones:buckets.vacaciones.size, incapacidades:buckets.incapacidades.size };
}
function justificadoPorArea(){
  const porArea = {};
  state.absences.forEach(a=>{
    const emp = state.employees.find(e=>e.id===a.employeeId);
    const area = emp ? emp.departamento : 'Sin área';
    if(!porArea[area]) porArea[area] = { justificado:0, noJustificado:0 };
    const dias = a.dias || (a.horas?a.horas/8:0);
    if(a.tipo==='Permiso NO justificado') porArea[area].noJustificado += dias;
    else porArea[area].justificado += dias;
  });
  return Object.entries(porArea).map(([area,v])=>({area, ...v, total:v.justificado+v.noJustificado}))
    .sort((a,b)=>b.total-a.total);
}

/* ======================= RENDER: SHELL / NAV ======================= */
const NAV_ITEMS = [
  {key:'dashboard', label:'Panorama general', icon:'grid'},
  {key:'personal', label:'Personal', icon:'folder'},
  {key:'ausentismo', label:'Ausentismo', icon:'calendar'},
  {key:'indicadores', label:'Indicadores', icon:'chart'}
];
const ICONS = {
  grid:'<rect x="3" y="3" width="7" height="7" rx="1"/><rect x="14" y="3" width="7" height="7" rx="1"/><rect x="3" y="14" width="7" height="7" rx="1"/><rect x="14" y="14" width="7" height="7" rx="1"/>',
  folder:'<path d="M3 6a1 1 0 0 1 1-1h5l2 2h9a1 1 0 0 1 1 1v10a1 1 0 0 1-1 1H4a1 1 0 0 1-1-1V6z"/>',
  calendar:'<rect x="3" y="5" width="18" height="16" rx="1"/><path d="M3 9h18M8 3v4M16 3v4"/>',
  chart:'<path d="M4 20V10M11 20V4M18 20v-7"/>'
};
function svgIcon(name){ return `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round" stroke-linejoin="round">${ICONS[name]}</svg>`; }

function renderNav(){
  const counts = {
    dashboard:'', personal:activeEmployees().length, ausentismo:state.absences.length, indicadores:''
  };
  document.getElementById('sidebarNav').innerHTML = NAV_ITEMS.map(it=>`
    <div class="nav-item ${state.page===it.key?'active':''}" data-page="${it.key}">
      ${svgIcon(it.icon)}<span>${it.label}</span>
      ${counts[it.key]!==''?`<span class="nav-count">${counts[it.key]}</span>`:''}
    </div>`).join('');
  document.querySelectorAll('.nav-item').forEach(el=>{
    el.addEventListener('click',()=>{ state.page = el.dataset.page; renderAll(); });
  });
}

function renderClock(){
  const now = new Date();
  document.getElementById('clock').textContent = now.toLocaleTimeString('es-HN',{hour:'2-digit',minute:'2-digit'});
  document.getElementById('today').textContent = now.toLocaleDateString('es-HN',{weekday:'long', day:'numeric', month:'long', year:'numeric'});
}
setInterval(renderClock,1000*30);

function renderAll(){
  renderNav();
  renderClock();
  const main = document.getElementById('main');
  if(state.page==='dashboard') main.innerHTML = pageDashboard();
  else if(state.page==='personal') main.innerHTML = pagePersonal();
  else if(state.page==='ausentismo') main.innerHTML = pageAusentismo();
  else if(state.page==='indicadores') main.innerHTML = pageIndicadores();
  bindPageEvents();
}

/* ======================= PÁGINA: DASHBOARD ======================= */
function pageDashboard(){
  const activos = state.employees.filter(e=>e.estado==='Activo').length;
  const licencia = state.employees.filter(e=>e.estado==='Licencia').length;
  const interinato = state.employees.filter(e=>e.estado==='Interinato').length;
  const bajas = state.employees.filter(e=>e.estado==='Baja').length;

  const now = new Date();
  const mesActual = now.toISOString().slice(0,7);
  const ausMes = state.absences.filter(a=> AUSENTISMO_TYPES.includes(a.tipo) && a.fechaInicio.slice(0,7)===mesActual);
  const diasAusMes = sumDias(ausMes);
  const diasLaborablesMes = 22;
  const baseEmpleados = Math.max(1, activeEmployees().length);
  const tasaAusentismo = ((diasAusMes/(baseEmpleados*diasLaborablesMes))*100).toFixed(1);

  const porCategoria = ABSENCE_TYPES.map(t=>({
    tipo:t, dias: sumDias(state.absences.filter(a=>a.tipo===t && a.fechaInicio.slice(0,7)===mesActual))
  })).filter(c=>c.dias>0).sort((a,b)=>b.dias-a.dias);
  const maxDias = Math.max(1,...porCategoria.map(c=>c.dias));

  const en30 = new Date(now.getTime()+30*86400000).toISOString().slice(0,10);
  const contratosPorVencer = state.employees.filter(e=>e.estado!=='Baja' && e.fechaFinContrato && e.fechaFinContrato<=en30 && e.fechaFinContrato>=todayISO());
  const vacacionesRiesgo = activeEmployees().filter(e=>saldoAnual(e)>=25);

  return `
  <div class="topbar">
    <div><div class="eyebrow">Actualizado en tiempo real</div><h2>Panorama general</h2></div>
  </div>

  <div class="grid grid-4" style="margin-bottom:16px;">
    <div class="card kpi accent"><div class="label">Personal activo</div><div class="value">${activos}</div><div class="sub">de ${state.employees.length} en archivo</div></div>
    <div class="card kpi amber"><div class="label">En licencia</div><div class="value">${licencia}</div><div class="sub">actualmente fuera</div></div>
    <div class="card kpi"><div class="label">Interinato</div><div class="value">${interinato}</div><div class="sub">cubriendo posiciones</div></div>
    <div class="card kpi red"><div class="label">Tasa de ausentismo</div><div class="value">${tasaAusentismo}%</div><div class="sub">mes en curso · ${diasAusMes} días</div></div>
  </div>

  <div class="grid grid-2">
    <div class="card">
      <h3>Días de ausencia por categoría — mes en curso</h3>
      ${porCategoria.length? porCategoria.map(c=>`
        <div class="bar-row">
          <div class="bar-label">${c.tipo}</div>
          <div class="bar-track"><div class="bar-fill" style="width:${(c.dias/maxDias*100).toFixed(0)}%"></div></div>
          <div class="bar-val">${c.dias}</div>
        </div>`).join('') : '<div class="empty-note">Aún no hay ausencias registradas este mes.</div>'}
    </div>
    <div class="card">
      <h3>Alertas</h3>
      ${contratosPorVencer.map(e=>`
        <div class="alert-item"><span>${e.nombre} — contrato vence ${fmtDate(e.fechaFinContrato)}</span><span class="alert-tag tag-amber">Contrato</span></div>
      `).join('')}
      ${vacacionesRiesgo.map(e=>`
        <div class="alert-item"><span>${e.nombre} — ${saldoAnual(e)} días de vacaciones acumulados</span><span class="alert-tag tag-red">Vacaciones</span></div>
      `).join('')}
      ${(contratosPorVencer.length+vacacionesRiesgo.length)===0 ? '<div class="empty-note">Sin alertas pendientes por ahora.</div>' : ''}
    </div>
  </div>
  `;
}

/* ======================= PÁGINA: PERSONAL ======================= */
function pagePersonal(){
  let list = state.employees.slice().sort((a,b)=>b.expediente-a.expediente);
  if(state.filterEstado!=='Todos') list = list.filter(e=>e.estado===state.filterEstado);
  if(state.searchTerm) list = list.filter(e=> (e.nombre+' '+(e.dni||'')+' '+(e.puestoFuncional||'')+' '+(e.puestoNominal||'')+' '+e.departamento).toLowerCase().includes(state.searchTerm.toLowerCase()));

  return `
  <div class="topbar">
    <div><div class="eyebrow">${activeEmployees().length} activos · ${state.employees.length} en total</div><h2>Expedientes de personal</h2></div>
    <div class="topbar-actions"><button class="btn btn-primary" id="btnNuevoEmpleado">+ Dar de alta</button></div>
  </div>

  <div class="toolbar">
    <input type="text" id="searchEmp" placeholder="Buscar por nombre, puesto o departamento…" value="${state.searchTerm}">
    <select id="filterEstado">
      ${['Todos','Activo','Licencia','Interinato','Baja'].map(s=>`<option ${state.filterEstado===s?'selected':''}>${s}</option>`).join('')}
    </select>
  </div>

  <div class="card" style="padding:0;">
    <div class="table-wrap">
    <table>
      <thead><tr>
        <th>Expediente</th><th>Nombre</th><th>DNI</th><th>Puesto funcional</th><th>Puesto nominal</th><th>Departamento</th>
        <th>Ingreso</th><th>Antigüedad</th><th>Estado</th><th>Saldo vacac.</th><th></th>
      </tr></thead>
      <tbody>
        ${list.length? list.map(e=>`
        <tr>
          <td class="mono">${expFmt(e.expediente)}</td>
          <td>${e.nombre}</td>
          <td class="mono">${e.dni||'—'}</td>
          <td>${e.puestoFuncional||'—'}</td>
          <td>${e.puestoNominal||'—'}</td>
          <td>${e.departamento}</td>
          <td class="mono">${fmtDate(e.fechaIngreso)}</td>
          <td>${e.estado==='Baja'?'—':antiguedadTxt(e.fechaIngreso)}</td>
          <td><span class="stamp stamp-${e.estado.toLowerCase()}">${e.estado}</span></td>
          <td class="num">${e.estado==='Baja'?'—':saldoAnual(e)}</td>
          <td><button class="btn btn-ghost btn-sm" data-verficha="${e.id}">Ver ficha</button></td>
        </tr>`).join('') : `<tr><td colspan="11"><div class="empty-note">Ningún expediente coincide. Prueba con otro filtro o da de alta al primer colaborador.</div></td></tr>`}
      </tbody>
    </table>
    </div>
  </div>
  `;
}

function pageFicha(empId){
  const e = state.employees.find(x=>x.id===empId);
  if(!e) { state.page='personal'; return pagePersonal(); }
  const historial = state.absences.filter(a=>a.employeeId===e.id).sort((a,b)=>b.fechaInicio.localeCompare(a.fechaInicio));

  return `
  <div class="topbar">
    <div><div class="eyebrow"><span id="volverPersonal" style="cursor:pointer; text-decoration:underline;">← Personal</span></div><h2>Ficha del expediente</h2></div>
  </div>

  <div class="ficha">
    <div class="ficha-top">
      <div>
        <div class="ficha-exp">${expFmt(e.expediente)} · DNI ${e.dni||'—'}</div>
        <div class="ficha-name">${e.nombre}</div>
        <div class="ficha-meta">${e.puestoFuncional||'—'} <span style="color:var(--ink-faint);">(nominal: ${e.puestoNominal||'—'})</span> · ${e.departamento} · ${e.tipoContrato||'—'} · Ingreso ${fmtDate(e.fechaIngreso)}${e.estado!=='Baja'?' · '+antiguedadTxt(e.fechaIngreso)+' de antigüedad':''}</div>
      </div>
      <span class="stamp stamp-${e.estado.toLowerCase()}">${e.estado}</span>
    </div>

    ${e.estado==='Baja' ? `<div class="empty-note">Baja el ${fmtDate(e.fechaBaja)} · Motivo: ${e.motivoBaja||'—'}</div>` : `
    <div class="ficha-grid">
      <div class="ficha-stat"><div class="label">Vacaciones anuales generadas</div><div class="val">${vacAccrued(e.fechaIngreso)} d</div></div>
      <div class="ficha-stat"><div class="label">Vacaciones anuales tomadas</div><div class="val">${sumDias(empAbsences(e.id,'Vacaciones anuales'))} d</div></div>
      <div class="ficha-stat"><div class="label">Saldo anual disponible</div><div class="val ${saldoAnual(e)<0?'deficit':''}">${saldoAnual(e)} d</div></div>
      <div class="ficha-stat"><div class="label">Saldo profilácticas</div><div class="val ${saldoProfilactico(e)<0?'deficit':''}">${saldoProfilactico(e)} d</div></div>
    </div>
    <div class="field-note">Escala usada (Código de Trabajo): 1 año = 10 d · 2 años = 12 d · 3 años = 15 d · 4+ años = 20 d por año. Ajuste manual actual: ${e.ajusteVacacional||0} d. Días profilácticos asignados: ${e.diasProfilacticos||0} d.</div>
    `}

    ${e.tipoContrato==='Permanencia' ? `
    <div class="section-title" style="font-size:12.5px; margin:16px 0 8px 0;">Datos de permanencia</div>
    <div class="ficha-grid" style="margin-top:0;">
      <div class="ficha-stat"><div class="label">Gerencia administrativa</div><div class="val" style="font-size:14px;">${e.gerenciaAdministrativa||'—'}</div></div>
      <div class="ficha-stat"><div class="label">Número de puesto</div><div class="val" style="font-size:14px;">${e.numeroPuesto||'—'}</div></div>
      <div class="ficha-stat"><div class="label">Grupo / Nivel</div><div class="val" style="font-size:14px;">${e.grupo||'—'} / ${e.nivel||'—'}</div></div>
      <div class="ficha-stat"><div class="label">Sueldo</div><div class="val" style="font-size:14px;">${e.sueldo? 'L. '+Number(e.sueldo).toLocaleString('es-HN'):'—'}</div></div>
    </div>` : ''}
    ${e.tipoContrato==='Definido' ? `
    <div class="section-title" style="font-size:12.5px; margin:16px 0 8px 0;">Datos de contrato</div>
    <div class="ficha-grid" style="margin-top:0;">
      <div class="ficha-stat"><div class="label">Número de contrato</div><div class="val" style="font-size:14px;">${e.numeroContrato||'—'}</div></div>
      <div class="ficha-stat"><div class="label">Sueldo</div><div class="val" style="font-size:14px;">${e.sueldo? 'L. '+Number(e.sueldo).toLocaleString('es-HN'):'—'}</div></div>
      <div class="ficha-stat"><div class="label">Fin de contrato</div><div class="val" style="font-size:14px;">${fmtDate(e.fechaFinContrato)}</div></div>
    </div>` : ''}
    ${(e.tipoContrato==='Interinato'||e.tipoContrato==='Por obra determinada') ? `
    <div class="field-note" style="margin-top:14px;">Fin de contrato: ${fmtDate(e.fechaFinContrato)}</div>` : ''}

    <div class="ficha-actions">
      ${e.estado!=='Baja' ? `<button class="btn btn-sm" data-registrarpara="${e.id}">Registrar ausencia</button>
      <button class="btn btn-sm" data-editarficha="${e.id}">Editar datos</button>
      <button class="btn btn-sm" data-cambiarestado="${e.id}">Cambiar estado</button>
      <button class="btn btn-sm btn-danger" data-baja="${e.id}">Dar de baja</button>` :
      `<button class="btn btn-sm" data-editarficha="${e.id}">Editar datos</button>`}
    </div>
  </div>

  <div class="section-title">Historial de ausencias</div>
  <div class="card" style="padding:0;">
    <div class="table-wrap">
    <table>
      <thead><tr><th>Tipo</th><th>Desde</th><th>Hasta</th><th>Días / Horas</th><th></th></tr></thead>
      <tbody>
        ${historial.length? historial.map(a=>`
        <tr>
          <td>${a.tipo}${a.nota?` <span class="field-note" style="display:inline;">(${a.nota})</span>`:''}</td>
          <td class="mono">${fmtDate(a.fechaInicio)}</td>
          <td class="mono">${fmtDate(a.fechaFin)}</td>
          <td class="num">${a.horas?a.horas+' h':a.dias+' d'}</td>
          <td><button class="btn btn-ghost btn-sm" data-delausencia="${a.id}">Eliminar</button></td>
        </tr>`).join('') : `<tr><td colspan="5"><div class="empty-note">Sin ausencias registradas todavía.</div></td></tr>`}
      </tbody>
    </table>
    </div>
  </div>
  `;
}

/* ======================= PÁGINA: AUSENTISMO ======================= */
function pageAusentismo(){
  let list = state.absences.slice().sort((a,b)=>b.fechaInicio.localeCompare(a.fechaInicio));
  if(state.filterAusEmp!=='Todos') list = list.filter(a=>a.employeeId===state.filterAusEmp);
  if(state.filterAusTipo!=='Todos') list = list.filter(a=>a.tipo===state.filterAusTipo);

  return `
  <div class="topbar">
    <div><div class="eyebrow">${state.absences.length} registros en total</div><h2>Registro de ausencias</h2></div>
    <div class="topbar-actions"><button class="btn btn-primary" id="btnNuevaAusencia">+ Registrar ausencia</button></div>
  </div>

  <div class="toolbar">
    <select id="filterAusEmp">
      <option value="Todos">Todo el personal</option>
      ${state.employees.map(e=>`<option value="${e.id}" ${state.filterAusEmp===e.id?'selected':''}>${e.nombre}</option>`).join('')}
    </select>
    <select id="filterAusTipo">
      <option>Todos</option>
      ${ABSENCE_TYPES.map(t=>`<option ${state.filterAusTipo===t?'selected':''}>${t}</option>`).join('')}
    </select>
  </div>

  <div class="card" style="padding:0;">
    <div class="table-wrap">
    <table>
      <thead><tr><th>Empleado</th><th>Tipo</th><th>Desde</th><th>Hasta</th><th>Días / Horas</th><th></th></tr></thead>
      <tbody>
        ${list.length? list.map(a=>{
          const emp = state.employees.find(e=>e.id===a.employeeId);
          return `<tr>
            <td>${emp?emp.nombre:'—'}</td>
            <td>${a.tipo}${a.nota?` <span class="field-note" style="display:inline;">(${a.nota})</span>`:''}</td>
            <td class="mono">${fmtDate(a.fechaInicio)}</td>
            <td class="mono">${fmtDate(a.fechaFin)}</td>
            <td class="num">${a.horas?a.horas+' h':a.dias+' d'}</td>
            <td><button class="btn btn-ghost btn-sm" data-delausencia="${a.id}">Eliminar</button></td>
          </tr>`;
        }).join('') : `<tr><td colspan="6"><div class="empty-note">No hay ausencias que coincidan con el filtro.</div></td></tr>`}
      </tbody>
    </table>
    </div>
  </div>
  `;
}

/* ======================= PÁGINA: INDICADORES ======================= */
function pageIndicadores(){
  const now = new Date();
  const mesActual = now.toISOString().slice(0,7);
  const ausMes = state.absences.filter(a=>AUSENTISMO_TYPES.includes(a.tipo) && a.fechaInicio.slice(0,7)===mesActual);
  const diasAusMes = sumDias(ausMes);
  const baseEmpleados = Math.max(1, activeEmployees().length);
  const tasaMensual = ((diasAusMes/(baseEmpleados*22))*100).toFixed(1);
  const promedioPorEmpleado = (diasAusMes/baseEmpleados).toFixed(1);

  const noJustificado = sumDias(state.absences.filter(a=>a.tipo==='Permiso NO justificado' && a.fechaInicio.slice(0,7)===mesActual));

  const porDepto = {};
  activeEmployees().forEach(e=>{ porDepto[e.departamento] = porDepto[e.departamento]||{dias:0,empleados:0}; porDepto[e.departamento].empleados++; });
  state.absences.filter(a=>AUSENTISMO_TYPES.includes(a.tipo) && a.fechaInicio.slice(0,7)===mesActual).forEach(a=>{
    const emp = state.employees.find(e=>e.id===a.employeeId);
    if(emp && porDepto[emp.departamento]) porDepto[emp.departamento].dias += a.dias;
  });
  const deptoRows = Object.entries(porDepto).sort((a,b)=>b[1].dias-a[1].dias);

  const buckets = personasEnCadaBucket();
  const plantilla = state.plantillaTotal || 337;
  const pct = n => ((n/plantilla)*100).toFixed(1);
  const areaStats = justificadoPorArea();
  const maxAreaTotal = Math.max(1,...areaStats.map(a=>a.total));

  return `
  <div class="topbar">
    <div><div class="eyebrow">Mes en curso y personalizados</div><h2>Indicadores</h2></div>
    <div class="topbar-actions">
      <label style="display:flex; align-items:center; gap:8px; font-size:12.5px; color:var(--ink-soft);">
        Plantilla autorizada
        <input type="number" min="1" id="inputPlantilla" value="${plantilla}" style="width:80px; padding:6px 9px; border:1px solid var(--line); border-radius:var(--radius);">
      </label>
    </div>
  </div>

  <div class="grid grid-4" style="margin-bottom:8px;">
    <div class="card kpi red"><div class="label">Tasa de ausentismo</div><div class="value">${tasaMensual}%</div><div class="sub">mes en curso</div></div>
    <div class="card kpi"><div class="label">Promedio por colaborador</div><div class="value">${promedioPorEmpleado}</div><div class="sub">días este mes</div></div>
    <div class="card kpi amber"><div class="label">Permisos no justificados</div><div class="value">${noJustificado}</div><div class="sub">días este mes</div></div>
    <div class="card kpi accent"><div class="label">Personal evaluado</div><div class="value">${baseEmpleados}</div><div class="sub">colaboradores activos</div></div>
  </div>

  <div class="section-title">Personal fuera de su puesto hoy — sobre plantilla de ${plantilla}</div>
  <div class="grid grid-4" style="margin-bottom:8px;">
    <div class="card kpi amber"><div class="label">En permisos</div><div class="value">${buckets.permisos}</div><div class="sub">${pct(buckets.permisos)}% de la plantilla</div></div>
    <div class="card kpi accent"><div class="label">En vacaciones</div><div class="value">${buckets.vacaciones}</div><div class="sub">${pct(buckets.vacaciones)}% de la plantilla</div></div>
    <div class="card kpi red"><div class="label">En incapacidad</div><div class="value">${buckets.incapacidades}</div><div class="sub">${pct(buckets.incapacidades)}% de la plantilla</div></div>
    <div class="card kpi"><div class="label">Total fuera hoy</div><div class="value">${buckets.permisos+buckets.vacaciones+buckets.incapacidades}</div><div class="sub">${pct(buckets.permisos+buckets.vacaciones+buckets.incapacidades)}% de la plantilla</div></div>
  </div>
  <div class="field-note" style="margin-bottom:20px;">"Permisos" agrupa: permiso por día, permiso no justificado, permiso por horas, duelo y maternidad. El conteo es de personas con una ausencia activa en la fecha de hoy.</div>

  <div class="section-title">Ausencias justificadas vs. no justificadas por área laboral</div>
  <div class="card">
    ${areaStats.length? `
    <div class="table-wrap">
    <table>
      <thead><tr><th>Área laboral</th><th>Justificadas (d)</th><th>No justificadas (d)</th><th>% no justificado</th><th style="min-width:160px;">Proporción</th></tr></thead>
      <tbody>
        ${areaStats.map(a=>`
        <tr>
          <td>${a.area}</td>
          <td class="num">${a.justificado.toFixed(1)}</td>
          <td class="num">${a.noJustificado.toFixed(1)}</td>
          <td class="num">${a.total? ((a.noJustificado/a.total)*100).toFixed(0):0}%</td>
          <td>
            <div class="bar-track" style="display:flex;">
              <div class="bar-fill" style="width:${(a.justificado/maxAreaTotal*100).toFixed(0)}%; background:var(--accent); border-radius:2px 0 0 2px;"></div><div class="bar-fill" style="width:${(a.noJustificado/maxAreaTotal*100).toFixed(0)}%; background:var(--red); border-radius:0 2px 2px 0;"></div>
            </div>
          </td>
        </tr>`).join('')}
      </tbody>
    </table>
    </div>
    <div class="field-note" style="margin-top:10px;"><span style="color:var(--accent-dark);">■</span> Justificadas &nbsp; <span style="color:var(--red);">■</span> No justificadas</div>
    ` : '<div class="empty-note">Registra ausencias con área laboral asignada para ver esta comparación.</div>'}
  </div>

  <div class="section-title">Ausentismo por departamento — mes en curso</div>
  <div class="card">
    ${deptoRows.length? deptoRows.map(([depto,d])=>{
      const maxD = Math.max(1,...deptoRows.map(r=>r[1].dias));
      return `<div class="bar-row">
        <div class="bar-label">${depto} (${d.empleados})</div>
        <div class="bar-track"><div class="bar-fill" style="width:${(d.dias/maxD*100).toFixed(0)}%"></div></div>
        <div class="bar-val">${d.dias}</div>
      </div>`;
    }).join('') : '<div class="empty-note">Registra departamentos y ausencias para ver esta comparación.</div>'}
  </div>

  <div class="section-title">Mis indicadores personalizados</div>
  <div style="margin-bottom:12px;"><button class="btn" id="btnNuevoIndicador">+ Agregar indicador</button></div>
  <div class="grid grid-2">
  ${state.indicators.length ? state.indicators.map(ind=>`
    <div class="indicator-card">
      <div class="txt"><div class="name">${ind.nombre}</div>${ind.nota?`<div class="note">${ind.nota}</div>`:''}</div>
      <div style="display:flex; align-items:center; gap:10px;">
        <div class="value">${ind.valor}${ind.unidad?(' '+ind.unidad):''}</div>
        <button class="btn btn-ghost btn-sm" data-delindicador="${ind.id}">✕</button>
      </div>
    </div>
  `).join('') : '<div class="empty-note">Aún no has agregado indicadores propios. Usa el botón de arriba para llevar el control de lo que te importa a ti.</div>'}
  </div>
  `;
}

/* ======================= MODALES ======================= */
function openModal(html){
  document.getElementById('modalBody').innerHTML = html;
  document.getElementById('overlay').classList.add('open');
}
function closeModal(){ document.getElementById('overlay').classList.remove('open'); }
document.getElementById('overlay').addEventListener('click', e=>{ if(e.target.id==='overlay') closeModal(); });

function modalNuevoEmpleado(){
  openModal(`
    <h3>Dar de alta</h3>
    <form id="formAlta">
      <div class="field-row">
        <div class="field"><label>Nombre completo</label><input required name="nombre"></div>
        <div class="field"><label>DNI (Documento Nacional de Identidad)</label><input required name="dni" placeholder="0000-0000-00000" maxlength="15"></div>
      </div>
      <div class="field-row">
        <div class="field"><label>Puesto funcional</label><input required name="puestoFuncional"></div>
        <div class="field"><label>Puesto nominal</label><input required name="puestoNominal"></div>
      </div>
      <div class="field"><label>Departamento</label><input required name="departamento"></div>
      <div class="field-row">
        <div class="field"><label>Fecha de ingreso</label><input required type="date" name="fechaIngreso" value="${todayISO()}"></div>
        <div class="field"><label>Tipo de contrato</label>
          <select name="tipoContrato" id="selTipoContrato">
            <option>Permanencia</option><option>Definido</option><option>Interinato</option><option>Por obra determinada</option>
          </select>
        </div>
      </div>
      <div class="field" id="wrapFechaFin" style="display:none;"><label>Fecha de fin de contrato</label><input type="date" name="fechaFinContrato"></div>

      <div id="wrapPermanencia" style="display:none;">
        <div class="field-row">
          <div class="field"><label>Gerencia administrativa</label><input name="gerenciaAdministrativa"></div>
          <div class="field"><label>Número de puesto</label><input name="numeroPuesto"></div>
        </div>
        <div class="field-row">
          <div class="field"><label>Grupo</label><input name="grupo"></div>
          <div class="field"><label>Nivel</label><input name="nivel"></div>
        </div>
        <div class="field"><label>Sueldo</label><input type="number" step="0.01" min="0" name="sueldoPermanencia"></div>
      </div>

      <div id="wrapDefinido" style="display:none;">
        <div class="field-row">
          <div class="field"><label>Sueldo</label><input type="number" step="0.01" min="0" name="sueldoDefinido"></div>
          <div class="field"><label>Número de contrato</label><input name="numeroContrato"></div>
        </div>
      </div>

      <div class="modal-actions">
        <button type="button" class="btn" onclick="closeModal()">Cancelar</button>
        <button type="submit" class="btn btn-primary">Dar de alta</button>
      </div>
    </form>
  `);
  const sel = document.getElementById('selTipoContrato');
  const toggleFin = ()=>{
    const v = sel.value;
    document.getElementById('wrapFechaFin').style.display = v==='Permanencia' ? 'none' : 'block';
    document.getElementById('wrapPermanencia').style.display = v==='Permanencia' ? 'block' : 'none';
    document.getElementById('wrapDefinido').style.display = v==='Definido' ? 'block' : 'none';
  };
  sel.addEventListener('change', toggleFin); toggleFin();

  document.getElementById('formAlta').addEventListener('submit', async e=>{
    e.preventDefault();
    const f = new FormData(e.target);
    state.expCounter += 1;
    const tipoContrato = f.get('tipoContrato');
    const estado = tipoContrato==='Interinato' ? 'Interinato' : 'Activo';
    const sueldo = tipoContrato==='Permanencia' ? f.get('sueldoPermanencia') : (tipoContrato==='Definido' ? f.get('sueldoDefinido') : null);
    const emp = {
      id:uid(), expediente:state.expCounter, dni:f.get('dni'),
      nombre:f.get('nombre'), puestoFuncional:f.get('puestoFuncional'), puestoNominal:f.get('puestoNominal'), departamento:f.get('departamento'),
      fechaIngreso:f.get('fechaIngreso'), tipoContrato,
      fechaFinContrato: tipoContrato==='Permanencia' ? null : (f.get('fechaFinContrato')||null),
      gerenciaAdministrativa: tipoContrato==='Permanencia' ? (f.get('gerenciaAdministrativa')||null) : null,
      numeroPuesto: tipoContrato==='Permanencia' ? (f.get('numeroPuesto')||null) : null,
      grupo: tipoContrato==='Permanencia' ? (f.get('grupo')||null) : null,
      nivel: tipoContrato==='Permanencia' ? (f.get('nivel')||null) : null,
      sueldo: sueldo ? Number(sueldo) : null,
      numeroContrato: tipoContrato==='Definido' ? (f.get('numeroContrato')||null) : null,
      estado, fechaBaja:null, motivoBaja:null,
      diasProfilacticos:0, ajusteVacacional:0
    };
    state.employees.push(emp);
    await saveKey('employees', state.employees);
    await saveKey('expCounter', state.expCounter);
    closeModal(); renderAll();
  });
}

function modalEditarFicha(empId){
  const e = state.employees.find(x=>x.id===empId);
  openModal(`
    <h3>Editar datos — ${e.nombre}</h3>
    <form id="formEditar">
      <div class="field-row">
        <div class="field"><label>Nombre completo</label><input required name="nombre" value="${e.nombre}"></div>
        <div class="field"><label>DNI</label><input required name="dni" value="${e.dni||''}" placeholder="0000-0000-00000" maxlength="15"></div>
      </div>
      <div class="field-row">
        <div class="field"><label>Puesto funcional</label><input required name="puestoFuncional" value="${e.puestoFuncional||''}"></div>
        <div class="field"><label>Puesto nominal</label><input required name="puestoNominal" value="${e.puestoNominal||''}"></div>
      </div>
      <div class="field"><label>Departamento</label><input required name="departamento" value="${e.departamento}"></div>

      ${e.tipoContrato==='Permanencia' ? `
      <div class="field-row">
        <div class="field"><label>Gerencia administrativa</label><input name="gerenciaAdministrativa" value="${e.gerenciaAdministrativa||''}"></div>
        <div class="field"><label>Número de puesto</label><input name="numeroPuesto" value="${e.numeroPuesto||''}"></div>
      </div>
      <div class="field-row">
        <div class="field"><label>Grupo</label><input name="grupo" value="${e.grupo||''}"></div>
        <div class="field"><label>Nivel</label><input name="nivel" value="${e.nivel||''}"></div>
      </div>
      <div class="field"><label>Sueldo</label><input type="number" step="0.01" min="0" name="sueldo" value="${e.sueldo||''}"></div>
      ` : ''}
      ${e.tipoContrato==='Definido' ? `
      <div class="field-row">
        <div class="field"><label>Sueldo</label><input type="number" step="0.01" min="0" name="sueldo" value="${e.sueldo||''}"></div>
        <div class="field"><label>Número de contrato</label><input name="numeroContrato" value="${e.numeroContrato||''}"></div>
      </div>
      ` : ''}

      <div class="field-row">
        <div class="field"><label>Días profilácticos asignados</label><input type="number" min="0" name="diasProfilacticos" value="${e.diasProfilacticos||0}"></div>
        <div class="field"><label>Ajuste manual vacaciones anuales (+/-)</label><input type="number" name="ajusteVacacional" value="${e.ajusteVacacional||0}"></div>
      </div>
      <div class="field-note">El ajuste manual corrige el cálculo automático si tu empresa usa una escala distinta a la del Código de Trabajo.</div>
      <div class="modal-actions">
        <button type="button" class="btn" onclick="closeModal()">Cancelar</button>
        <button type="submit" class="btn btn-primary">Guardar cambios</button>
      </div>
    </form>
  `);
  document.getElementById('formEditar').addEventListener('submit', async ev=>{
    ev.preventDefault();
    const f = new FormData(ev.target);
    e.nombre=f.get('nombre'); e.dni=f.get('dni'); e.puestoFuncional=f.get('puestoFuncional'); e.puestoNominal=f.get('puestoNominal'); e.departamento=f.get('departamento');
    if(e.tipoContrato==='Permanencia'){
      e.gerenciaAdministrativa=f.get('gerenciaAdministrativa')||null;
      e.numeroPuesto=f.get('numeroPuesto')||null;
      e.grupo=f.get('grupo')||null;
      e.nivel=f.get('nivel')||null;
      e.sueldo=f.get('sueldo')?Number(f.get('sueldo')):null;
    }
    if(e.tipoContrato==='Definido'){
      e.sueldo=f.get('sueldo')?Number(f.get('sueldo')):null;
      e.numeroContrato=f.get('numeroContrato')||null;
    }
    e.diasProfilacticos=Number(f.get('diasProfilacticos'))||0;
    e.ajusteVacacional=Number(f.get('ajusteVacacional'))||0;
    await saveKey('employees', state.employees);
    closeModal(); renderFicha();
  });
}

function modalCambiarEstado(empId){
  const e = state.employees.find(x=>x.id===empId);
  openModal(`
    <h3>Cambiar estado — ${e.nombre}</h3>
    <form id="formEstado">
      <div class="field"><label>Nuevo estado</label>
        <select name="estado">
          ${['Activo','Licencia','Interinato'].map(s=>`<option ${e.estado===s?'selected':''}>${s}</option>`).join('')}
        </select>
      </div>
      <div class="modal-actions">
        <button type="button" class="btn" onclick="closeModal()">Cancelar</button>
        <button type="submit" class="btn btn-primary">Guardar</button>
      </div>
    </form>
  `);
  document.getElementById('formEstado').addEventListener('submit', async ev=>{
    ev.preventDefault();
    e.estado = new FormData(ev.target).get('estado');
    await saveKey('employees', state.employees);
    closeModal(); renderFicha();
  });
}

function modalBaja(empId){
  const e = state.employees.find(x=>x.id===empId);
  openModal(`
    <h3>Dar de baja — ${e.nombre}</h3>
    <form id="formBaja">
      <div class="field"><label>Fecha de baja</label><input required type="date" name="fechaBaja" value="${todayISO()}"></div>
      <div class="field"><label>Motivo</label>
        <select name="motivoBaja"><option>Despido</option><option>Renuncia</option><option>Terminación de contrato</option><option>Otro</option></select>
      </div>
      <div class="modal-actions">
        <button type="button" class="btn" onclick="closeModal()">Cancelar</button>
        <button type="submit" class="btn btn-danger">Confirmar baja</button>
      </div>
    </form>
  `);
  document.getElementById('formBaja').addEventListener('submit', async ev=>{
    ev.preventDefault();
    const f = new FormData(ev.target);
    e.estado='Baja'; e.fechaBaja=f.get('fechaBaja'); e.motivoBaja=f.get('motivoBaja');
    await saveKey('employees', state.employees);
    closeModal(); renderFicha();
  });
}

function modalNuevaAusencia(preEmpId){
  const preEmp = preEmpId ? state.employees.find(e=>e.id===preEmpId) : null;
  openModal(`
    <h3>Registrar ausencia</h3>
    <form id="formAusencia">
      <div class="field" id="empSearchWrap" style="position:relative;">
        <label>Empleado</label>
        <input type="text" id="empSearchInput" autocomplete="off" placeholder="Escribe el nombre o DNI…" value="${preEmp?preEmp.nombre:''}">
        <input type="hidden" name="employeeId" id="empSearchId" value="${preEmpId||''}">
        <div id="empSearchList" class="autocomplete-list" style="display:none;"></div>
      </div>
      <div class="field"><label>Tipo de ausencia</label>
        <select required name="tipo" id="selTipoAus">${ABSENCE_TYPES.map(t=>`<option>${t}</option>`).join('')}</select>
      </div>
      <div id="wrapFechas" class="field-row">
        <div class="field"><label>Desde</label><input required type="date" name="fechaInicio" value="${todayISO()}"></div>
        <div class="field"><label>Hasta</label><input required type="date" name="fechaFin" value="${todayISO()}"></div>
      </div>
      <div id="wrapHoras" class="field" style="display:none;">
        <label>Fecha</label><input type="date" name="fechaHoras" value="${todayISO()}">
        <label style="margin-top:10px;">Horas (1–6)</label>
        <input type="number" name="horas" min="1" max="12" value="1">
        <div class="field-note">Si registras más de 6 horas, el sistema lo convertirá automáticamente en un Permiso por día completo.</div>
      </div>
      <div class="modal-actions">
        <button type="button" class="btn" onclick="closeModal()">Cancelar</button>
        <button type="submit" class="btn btn-primary">Registrar</button>
      </div>
    </form>
  `);

  const elegibles = state.employees.filter(e=>e.estado!=='Baja');
  const empInput = document.getElementById('empSearchInput');
  const empHidden = document.getElementById('empSearchId');
  const empList = document.getElementById('empSearchList');
  const renderEmpOptions = term=>{
    const t = term.trim().toLowerCase();
    const matches = t ? elegibles.filter(e=>(e.nombre+' '+(e.dni||'')).toLowerCase().includes(t)) : elegibles;
    if(!matches.length){ empList.innerHTML = '<div class="autocomplete-empty">Sin coincidencias</div>'; empList.style.display='block'; return; }
    empList.innerHTML = matches.slice(0,40).map(e=>`
      <div class="autocomplete-item" data-id="${e.id}">${e.nombre}
        <div class="field-note">${e.dni?'DNI '+e.dni+' · ':''}${e.departamento}</div>
      </div>`).join('');
    empList.style.display='block';
  };
  empInput.addEventListener('focus', ()=>renderEmpOptions(empInput.value));
  empInput.addEventListener('input', ()=>{ empHidden.value=''; renderEmpOptions(empInput.value); });
  empList.addEventListener('click', e=>{
    const item = e.target.closest('.autocomplete-item');
    if(!item) return;
    const emp = elegibles.find(x=>x.id===item.dataset.id);
    if(!emp) return;
    empInput.value = emp.nombre; empHidden.value = emp.id; empList.style.display='none';
  });
  document.addEventListener('click', e=>{ if(!e.target.closest('#empSearchWrap')) empList.style.display='none'; });

  const selTipo = document.getElementById('selTipoAus');
  const toggle = ()=>{
    const esHoras = selTipo.value==='Permiso por horas';
    document.getElementById('wrapFechas').style.display = esHoras?'none':'grid';
    document.getElementById('wrapHoras').style.display = esHoras?'block':'none';
  };
  selTipo.addEventListener('change', toggle); toggle();

  document.getElementById('formAusencia').addEventListener('submit', async ev=>{
    ev.preventDefault();
    if(!empHidden.value){ alert('Escribe y selecciona un empleado de la lista.'); return; }
    const f = new FormData(ev.target);
    let tipo = f.get('tipo');
    let fechaInicio, fechaFin, dias, horas=null, nota=null;

    if(tipo==='Permiso por horas'){
      const h = Number(f.get('horas'));
      fechaInicio = f.get('fechaHoras'); fechaFin = f.get('fechaHoras');
      if(h>6){ tipo='Permiso por día'; dias=1; nota=`convertido automáticamente: se solicitaron ${h} h`; }
      else { horas=h; dias=0; }
    } else {
      fechaInicio = f.get('fechaInicio'); fechaFin = f.get('fechaFin');
      if(fechaFin<fechaInicio){ alert('La fecha "hasta" no puede ser anterior a "desde".'); return; }
      dias = daysBetween(fechaInicio, fechaFin);
    }

    state.absences.push({ id:uid(), employeeId:f.get('employeeId'), tipo, fechaInicio, fechaFin, dias, horas, nota, createdAt:todayISO() });
    await saveKey('absences', state.absences);
    closeModal();
    if(preEmpId && state.viewingFicha===preEmpId) renderFicha(); else renderAll();
  });
}

function modalNuevoIndicador(){
  openModal(`
    <h3>Agregar indicador</h3>
    <form id="formIndicador">
      <div class="field"><label>Nombre del indicador</label><input required name="nombre" placeholder="p. ej. Rotación de personal"></div>
      <div class="field-row">
        <div class="field"><label>Valor</label><input required name="valor" placeholder="p. ej. 4.2"></div>
        <div class="field"><label>Unidad (opcional)</label><input name="unidad" placeholder="p. ej. %"></div>
      </div>
      <div class="field"><label>Nota (opcional)</label><input name="nota" placeholder="Contexto o fuente del dato"></div>
      <div class="modal-actions">
        <button type="button" class="btn" onclick="closeModal()">Cancelar</button>
        <button type="submit" class="btn btn-primary">Agregar</button>
      </div>
    </form>
  `);
  document.getElementById('formIndicador').addEventListener('submit', async ev=>{
    ev.preventDefault();
    const f = new FormData(ev.target);
    state.indicators.push({ id:uid(), nombre:f.get('nombre'), valor:f.get('valor'), unidad:f.get('unidad'), nota:f.get('nota') });
    await saveKey('indicators', state.indicators);
    closeModal(); renderAll();
  });
}

/* ======================= EVENTOS DE PÁGINA ======================= */
function bindPageEvents(){
  const $ = sel=>document.querySelector(sel);

  if(state.page==='personal'){
    $('#btnNuevoEmpleado')?.addEventListener('click', modalNuevoEmpleado);
    $('#searchEmp')?.addEventListener('input', e=>{ state.searchTerm=e.target.value; renderAll(); document.getElementById('searchEmp').focus(); document.getElementById('searchEmp').selectionStart = document.getElementById('searchEmp').value.length; });
    $('#filterEstado')?.addEventListener('change', e=>{ state.filterEstado=e.target.value; renderAll(); });
    document.querySelectorAll('[data-verficha]').forEach(b=>b.addEventListener('click',()=>{ state.viewingFicha=b.dataset.verficha; renderFicha(); }));
  }

  if(state.page==='ausentismo'){
    $('#btnNuevaAusencia')?.addEventListener('click', ()=>modalNuevaAusencia(null));
    $('#filterAusEmp')?.addEventListener('change', e=>{ state.filterAusEmp=e.target.value; renderAll(); });
    $('#filterAusTipo')?.addEventListener('change', e=>{ state.filterAusTipo=e.target.value; renderAll(); });
    document.querySelectorAll('[data-delausencia]').forEach(b=>b.addEventListener('click', async ()=>{
      state.absences = state.absences.filter(a=>a.id!==b.dataset.delausencia);
      await saveKey('absences', state.absences); renderAll();
    }));
  }

  if(state.page==='indicadores'){
    $('#btnNuevoIndicador')?.addEventListener('click', modalNuevoIndicador);
    $('#inputPlantilla')?.addEventListener('change', async e=>{
      const v = Number(e.target.value)||337;
      state.plantillaTotal = v;
      await saveKey('plantillaTotal', v);
      renderAll();
    });
    document.querySelectorAll('[data-delindicador]').forEach(b=>b.addEventListener('click', async ()=>{
      state.indicators = state.indicators.filter(i=>i.id!==b.dataset.delindicador);
      await saveKey('indicators', state.indicators); renderAll();
    }));
  }
}

function renderFicha(){
  renderNav(); renderClock();
  document.getElementById('main').innerHTML = pageFicha(state.viewingFicha);
  bindFichaEvents();
}

function bindFichaEvents(){
  document.getElementById('volverPersonal')?.addEventListener('click', ()=>{ state.page='personal'; state.viewingFicha=null; renderAll(); });
  document.querySelectorAll('[data-registrarpara]').forEach(b=>b.addEventListener('click',()=>modalNuevaAusencia(b.dataset.registrarpara)));
  document.querySelectorAll('[data-editarficha]').forEach(b=>b.addEventListener('click',()=>modalEditarFicha(b.dataset.editarficha)));
  document.querySelectorAll('[data-cambiarestado]').forEach(b=>b.addEventListener('click',()=>modalCambiarEstado(b.dataset.cambiarestado)));
  document.querySelectorAll('[data-baja]').forEach(b=>b.addEventListener('click',()=>modalBaja(b.dataset.baja)));
  document.querySelectorAll('[data-delausencia]').forEach(b=>b.addEventListener('click', async ()=>{
    state.absences = state.absences.filter(a=>a.id!==b.dataset.delausencia);
    await saveKey('absences', state.absences);
    renderFicha();
  }));
}

/* ======================= INICIO ======================= */
/* La carga inicial la dispara auth.onAuthStateChanged() más arriba */
</script>
</body>
</html>
