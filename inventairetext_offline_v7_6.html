<!doctype html>
<html lang="fr">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Inventaire Pemsa — v7.5</title>
<style>
  :root{--bg:#0e1116;--fg:#e6edf3;--muted:#9aa4b2;--card:#161b22;--border:#263241;--btn:#243042;--primary:#0ea5a4;--danger:#ef4444}
  *{box-sizing:border-box}
  body{margin:0;background:var(--bg);color:var(--fg);font:15px/1.45 -apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica,Arial,sans-serif}
  .wrap{max-width:1200px;margin:0 auto;padding:14px}
  .row{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
  .card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:12px}
  .btn{background:var(--btn);color:var(--fg);border:1px solid var(--border);padding:8px 12px;border-radius:12px;cursor:pointer;min-height:36px;font-weight:600;white-space:nowrap}
  .btn-primary{background:var(--primary);color:#062c2c;border-color:transparent}
  .btn-danger{background:var(--danger);color:#fff;border-color:transparent}
  .badge,.tag{display:inline-block;background:#1b2330;border:1px solid var(--border);padding:2px 8px;border-radius:999px;font-size:12px;color:var(--muted)}
  .field{display:flex;flex-direction:column;gap:6px;min-width:220px;flex:1}
  label{color:var(--muted);font-size:12px}
  input,select,textarea{background:#111722;color:var(--fg);border:1px solid var(--border);border-radius:10px;padding:10px;min-height:40px}
  textarea{min-height:96px}
  .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:10px}
  .title{font-weight:800;font-size:18px}
  .list{max-height:60vh;overflow:auto;display:grid;gap:8px}
  .tbl{width:100%;border-collapse:collapse}
  .tbl th,.tbl td{border-bottom:1px solid var(--border);padding:8px 6px;text-align:left}
  .tbl thead th{position:sticky;top:0;background:#0f1622}
  .toast{position:fixed;left:50%;transform:translateX(-50%);bottom:18px;background:#0a0f15;border:1px solid var(--border);padding:10px 12px;border-radius:10px;z-index:10000;display:none}
  #modal{position:fixed;inset:0;display:none;z-index:9999}
  #modal.show{display:block}
  #overlay{position:absolute;inset:0;background:rgba(0,0,0,.45)}
  #mcard{position:relative;max-width:980px;margin:40px auto;background:var(--card);border:1px solid var(--border);border-radius:14px;padding:12px}
  .date-wrap{position:relative}
  .date-icon{position:absolute;right:8px;top:50%;transform:translateY(-50%);display:flex;gap:6px}
  .date-icon svg{width:20px;height:20px}
  .cal-att svg{fill:var(--primary)}
  .cal-ret svg{fill:var(--danger)}
  #status{position:fixed;right:10px;top:10px;padding:4px 8px;border-radius:999px;font-size:12px;border:1px solid var(--border);background:#0f1a12}
  #status.err{background:#2a0f12}
  #photoPrev{max-width:100%;max-height:140px;border:1px solid var(--border);border-radius:10px;display:block}
  .lock{opacity:.7;pointer-events:none}
  @media (max-width:520px){ .field{min-width:auto} .btn{width:100%} }
</style>
</head>
<body>
<div id="status">JS: <b id="jsState">init…</b> • <span id="offline" class="tag">Offline</span></div>
<div class="wrap">
  <div class="row" style="justify-content:space-between">
    <div class="title">Inventaire Pemsa <span class="tag">v7.5</span> <span class="badge">Offline</span></div>
    <div class="row">
      <button class="btn" id="btnExportCSV">Export CSV</button>
      <button class="btn" id="btnExportHistGlobal">Export Historique</button>
      <button class="btn" id="btnToolsCSV">Outils CSV</button>
      <button class="btn" id="btnLists">Gérer listes</button>
    </div>
  </div>

  <div class="card" style="margin-top:10px">
    <div class="grid">
      <div class="field" style="grid-column: span 2">
        <label>Rechercher…</label>
        <div class="row">
          <input id="q" style="flex:1" placeholder="QR, N° série, outil, collaborateur, conseiller, catégorie…">
          <button class="btn" id="btnSearch">Rechercher</button>
        </div>
      </div>
      <div class="field"><label>Catégorie</label><select id="fCat"></select></div>
      <div class="field"><label>Statut</label><select id="fStat"></select></div>
      <div class="field"><label>Collaborateur</label><select id="fCol"></select></div>
      <div class="field"><label>Conseiller</label><select id="fCon"></select></div>
    </div>
    <div class="row" style="margin-top:8px">
      <button class="btn" id="btnReset">Effacer filtres</button>
      <div id="resCount" class="tag"></div>
      <div id="autosave" class="tag">Autosave: <span id="autosaveState">—</span></div>
    </div>
  </div>

  <div class="grid" style="margin-top:10px">
    <div class="card">
      <div class="row" style="justify-content:space-between">
        <div class="title">Fiche outil</div>
        <div class="row">
          <button class="btn btn-primary" id="btnCreate">Créer</button>
          <button class="btn" id="btnDup">Dupliquer</button>
          <button class="btn" id="btnSave">Enregistrer</button>
          <button class="btn" id="btnFindQR">Rechercher QR</button>
          <button class="btn btn-danger" id="btnDelete">Supprimer</button>
        </div>
      </div>
      <div class="grid" style="margin-top:6px">
        <div class="field"><label>— Choisir —</label><select id="selTool"></select></div>
        <div class="field"><label>Nom de l’outil</label><input id="nom"></div>
        <div class="field"><label>Numéro de série</label><input id="numeroSerie"></div>
        <div class="field">
          <label>QR Code</label>
          <div class="row">
            <input id="qrCode" style="flex:1">
            <button class="btn" id="btnScanLive">Scanner (live)</button>
            <label class="btn" for="qrPhoto">Scanner (photo)</label>
            <input id="qrPhoto" type="file" accept="image/*" style="display:none">
          </div>
        </div>
        <div class="field"><label>Conseiller Pemsa</label><select id="conseiller"></select></div>
        <div class="field"><label>Catégorie</label><select id="categorie"></select></div>
        <div class="field"><label>Collaborateur</label><select id="collaborateur"></select></div>
        <div class="field"><label>Statut</label><select id="statut"></select></div>
        <div class="field date-wrap">
          <label>Date d'attribution</label>
          <input id="dateAttribution" type="date">
          <div class="date-icon"><button class="cal-att" id="iconAtt" title="Choisir une date (Attribution)"><svg viewBox="0 0 24 24"><path d="M7 2h2v2h6V2h2v2h3v18H4V4h3V2zm13 6H6v12h14V8zM8 10h4v4H8v-4z"/></svg></button></div>
        </div>
        <div class="field date-wrap">
          <label>Date de retour</label>
          <input id="dateRetour" type="date">
          <div class="date-icon"><button class="cal-ret" id="iconRet" title="Choisir une date (Retour)"><svg viewBox="0 0 24 24"><path d="M7 2h2v2h6V2h2v2h3v18H4V4h3V2zm13 6H6v12h14V8zM12 10h4v4h-4v-4z"/></svg></button></div>
        </div>
        <div class="field"><label>Photo de l’outil</label>
          <div class="row" style="align-items:flex-start">
            <img id="photoPrev" alt="aperçu" />
            <label class="btn" for="photoInp">Ajouter photo</label>
            <input id="photoInp" type="file" accept="image/*" style="display:none" />
            <button class="btn" id="photoDel">Supprimer photo</button>
          </div>
        </div>
        <div class="field" style="grid-column: span 2"><label>Infos complémentaires</label><textarea id="infos"></textarea></div>
        <div class="field" style="grid-column: span 2"><label>Observations</label><textarea id="observations"></textarea></div>
      </div>

      <div class="row" style="margin-top:10px;flex-wrap:wrap">
        <button class="btn" id="btnCloseReassign">Clôturer & réaffecter</button>
        <button class="btn" id="btnPrint">Imprimer fiche</button>
        <button class="btn" id="btnPDF">PDF fiche</button>
        <button class="btn" id="btnPrintHist">Imprimer historique</button>
        <button class="btn" id="btnPDFHist">PDF historique</button>
        <button class="btn" id="btnExportHistTool">Export hist (outil)</button>
        <button class="btn" id="btnUnlock">Déverrouiller</button>
        <button class="btn" id="btnUndo" title="Annuler dernière action">Annuler</button>
      </div>

      <div class="title" style="margin-top:10px">Historique</div>
      <div class="row" style="margin:6px 0">
        <select id="histAction">
          <option>Note</option><option>Attribution</option><option>Retour</option>
          <option>Maintenance</option><option>Réparation</option><option>Perte</option>
          <option>Clôture</option><option>Autre</option>
        </select>
        <input id="histDetail" placeholder="Détail complément (facultatif)" style="flex:1">
        <button class="btn" id="btnAddHist">Ajouter</button>
      </div>
      <div id="hist" class="list"></div>
    </div>

    <div class="card">
      <div class="row" style="justify-content:space-between">
        <div class="title">Résultats</div>
        <div class="row">
          <button class="btn" id="btnSelectAll">Tout sélectionner</button>
          <button class="btn btn-danger" id="btnBulkDelete">Supprimer sélection</button>
        </div>
      </div>
      <div id="results" class="list" style="margin-top:6px"></div>
    </div>
  </div>
</div>

<!-- MODALE GESTION LISTES -->
<div id="modal">
  <div id="overlay"></div>
  <div id="mcard">
    <div class="row" style="justify-content:space-between">
      <div class="title">Gérer les listes</div>
      <button class="btn btn-danger" id="btnCloseModal">Fermer</button>
    </div>
    <div class="row" style="margin-top:10px">
      <button class="btn" data-tab="collabs">Collaborateurs</button>
      <button class="btn" data-tab="cons">Conseillers</button>
      <button class="btn" data-tab="cats">Catégories</button>
    </div>

    <div id="tab-collabs" class="card" style="margin-top:10px">
      <div class="row">
        <input id="cId" placeholder="ID (ex. 8176)" style="max-width:140px">
        <input id="cFirst" placeholder="Prénom">
        <input id="cLast" placeholder="Nom">
        <button class="btn btn-primary" id="cAdd">Ajouter</button>
        <button class="btn btn-danger" id="cDel">Supprimer sélection</button>
        <label class="btn" for="cCSV">Importer CSV</label><input id="cCSV" type="file" accept=".csv" style="display:none">
        <button class="btn" id="cExport">Export CSV</button>
        <button class="btn" id="cExportJSON">Export JSON</button>
        <label class="btn" for="cJSON">Importer JSON</label><input id="cJSON" type="file" accept="application/json" style="display:none">
      </div>
      <div style="max-height:45vh;overflow:auto;margin-top:8px">
        <table class="tbl" id="cTable">
          <thead><tr><th><input type="checkbox" id="cAll"></th><th>Numéro</th><th>Prénom</th><th>Nom</th></tr></thead>
          <tbody></tbody>
        </table>
      </div>
    </div>

    <div id="tab-cons" class="card" style="margin-top:10px;display:none">
      <div class="row">
        <input id="sName" placeholder="Nom du conseiller">
        <button class="btn btn-primary" id="sAdd">Ajouter</button>
        <button class="btn btn-danger" id="sDel">Supprimer sélection</button>
        <label class="btn" for="sCSV">Importer CSV</label><input id="sCSV" type="file" accept=".csv" style="display:none">
        <button class="btn" id="sExport">Export CSV</button>
        <button class="btn" id="sExportJSON">Export JSON</button>
        <label class="btn" for="sJSON">Importer JSON</label><input id="sJSON" type="file" accept="application/json" style="display:none">
      </div>
      <div style="max-height:45vh;overflow:auto;margin-top:8px">
        <table class="tbl" id="sTable">
          <thead><tr><th><input type="checkbox" id="sAll"></th><th>Conseiller</th></tr></thead>
          <tbody></tbody>
        </table>
      </div>
    </div>

    <div id="tab-cats" class="card" style="margin-top:10px;display:none">
      <div class="row">
        <input id="catName" placeholder="Nouvelle catégorie">
        <button class="btn btn-primary" id="catAdd">Ajouter</button>
        <button class="btn btn-danger" id="catDel">Supprimer sélection</button>
        <label class="btn" for="catCSV">Importer CSV</label><input id="catCSV" type="file" accept=".csv" style="display:none">
        <button class="btn" id="catExport">Export CSV</button>
        <button class="btn" id="catExportJSON">Export JSON</button>
        <label class="btn" for="catJSON">Importer JSON</label><input id="catJSON" type="file" accept="application/json" style="display:none">
      </div>
      <div style="max-height:45vh;overflow:auto;margin-top:8px">
        <table class="tbl" id="catTable">
          <thead><tr><th><input type="checkbox" id="catAll"></th><th>Catégorie</th></tr></thead>
          <tbody></tbody>
        </table>
      </div>
    </div>

  </div>
</div>

<div id="toast" class="toast"></div>

<script>
(function(){
  function onReady(fn){ if(document.readyState!=='loading') fn(); else document.addEventListener('DOMContentLoaded', fn,{once:true}); }
  onReady(init);

  function init(){
    const jsState = document.getElementById('jsState');
    try{
      const STORAGE_KEY='pemsa_inv_v7_5';
      const $=(s,r=document)=>r.querySelector(s), $$=(s,r=document)=>Array.from(r.querySelectorAll(s));
      const toast=(m)=>{ const t=$("#toast"); t.textContent=m; t.style.display="block"; setTimeout(()=>t.style.display="none",1500); };
      const todayISO=()=>new Date().toISOString().slice(0,10);
      const uid=()=>Math.random().toString(36).slice(2);
      const esc=(s)=>String(s||'').replace(/[&<>"']/g, m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]));

      // ---- modèle ----
      function defaults(){return{outils:[],categories:['Perceuse','Perforateur','Disqueuse','Mesure','Divers'],collaborateurs:[],conseillers:[]}};
      function load(){ try{return Object.assign(defaults(), JSON.parse(localStorage.getItem(STORAGE_KEY)||'{}'))}catch(e){return defaults()}};
      function save(){ localStorage.setItem(STORAGE_KEY, JSON.stringify(model)); lastSaved=new Date(); $("#autosaveState").textContent = lastSaved.toLocaleTimeString(); }
      function backup(){ localStorage.setItem(STORAGE_KEY+'_backup', JSON.stringify(model)); }
      function restore(){ const raw=localStorage.getItem(STORAGE_KEY+'_backup'); if(raw){ model=Object.assign(defaults(), JSON.parse(raw)); save(); renderAll(); toast('Restauration (backup)'); } }

      function download(name,content,type){ const u=URL.createObjectURL(new Blob([content],{type})); const a=document.createElement('a'); a.href=u; a.download=name; document.body.appendChild(a); a.click(); a.remove(); setTimeout(()=>URL.revokeObjectURL(u),1200) };
      function parseCSV(text){ const lines=text.split(/\r?\n/).filter(Boolean); if(!lines.length) return []; const sep=(text.indexOf(';')>-1 && text.indexOf(',')==-1)?';':','; const head=lines.shift().split(sep).map(h=>h.trim()); return lines.map(l=>{ const cells=l.split(sep).map(x=>x.trim()); const o={}; head.forEach((h,i)=>o[h]=cells[i]||''); return o; }); }

      let model=load();
      let undoStack=[]; let lastSaved=null;

      const statuts=['En service','Attribué','En réparation','Perdu','Hors service','Clôturé'];

      // ---- éléments ----
      const selTool=$('#selTool');
      const inputs={nom:$('#nom'),numeroSerie:$('#numeroSerie'),qrCode:$('#qrCode'),conseiller:$('#conseiller'),categorie:$('#categorie'),collaborateur:$('#collaborateur'),statut:$('#statut'),dateAttribution:$('#dateAttribution'),dateRetour:$('#dateRetour'),infos:$('#infos'),observations:$('#observations'),photoPrev:$('#photoPrev')};
      const filters={q:$('#q'),fCat:$('#fCat'),fStat:$('#fStat'),fCol:$('#fCol'),fCon:$('#fCon')};
      const histDiv=$('#hist'),resDiv=$('#results'),resCount=$('#resCount');

      function fillSelect(sel, items, first=null, all=false){
        sel.innerHTML=''; if(first!==null){ const o=document.createElement('option'); o.value=''; o.textContent=first||'— Choisir —'; sel.appendChild(o); }
        (all?['Tous',...items]:items).forEach(v=>{ const op=document.createElement('option'); op.value=v; op.textContent=v; sel.appendChild(op); });
      }
      function refreshSelectors(){
        fillSelect(filters.fCat, model.categories, 'Catégorie — Toutes', true);
        fillSelect(filters.fStat, statuts, 'Tous', true);
        fillSelect(filters.fCol, model.collaborateurs.map(c=>c.id?`${c.id} — ${c.first||''} — ${c.last||''}`:c), 'Tous', true);
        fillSelect(filters.fCon, model.conseillers, 'Tous', true);
        fillSelect(inputs.categorie, model.categories, '— Choisir —', false);
        fillSelect(inputs.collaborateur, model.collaborateurs.map(c=>c.id?`${c.id} — ${c.first||''} — ${c.last||''}`:c), '— Choisir —', false);
        fillSelect(inputs.conseiller, model.conseillers, '— Choisir —', false);
        fillSelect(inputs.statut, statuts, null, false);
      }

      function filtered(){
        const q=(filters.q.value||'').toLowerCase();
        return model.outils.filter(o=>{
          const okQ=!q||[o.qrCode,o.numeroSerie,o.nom,o.categorie,o.collaborateur,o.conseiller].some(v=>String(v||'').toLowerCase().includes(q));
          const okCat=!filters.fCat.value||filters.fCat.value==='Tous'||o.categorie===filters.fCat.value;
          const okSt=!filters.fStat.value||filters.fStat.value==='Tous'||o.statut===filters.fStat.value;
          const okCol=!filters.fCol.value||filters.fCol.value==='Tous'||o.collaborateur===filters.fCol.value;
          const okCon=!filters.fCon.value||filters.fCon.value==='Tous'||o.conseiller===filters.fCon.value;
          return okQ&&okCat&&okSt&&okCol&&okCon;
        });
      }

      function renderResults(){
        const list=filtered(); resDiv.innerHTML=''; selTool.innerHTML='';
        const o0=document.createElement('option'); o0.value=''; o0.textContent='(sélectionner)'; selTool.appendChild(o0);
        list.forEach(o=>{
          const opt=document.createElement('option'); opt.value=o.id; opt.textContent=o.nom||o.qrCode||o.numeroSerie||o.id; selTool.appendChild(opt);
          const row=document.createElement('div'); row.style.cssText='border:1px solid var(--border);border-radius:10px;padding:8px';
          row.innerHTML=`<label style="display:flex;gap:8px;align-items:center">
            <input type="checkbox" data-id="${o.id}">
            <div style="flex:1">
              <div><strong>${esc(o.nom||'(sans nom)')}</strong> <span class="tag">${esc(o.categorie||'-')}</span></div>
              <div class="tag">QR: ${esc(o.qrCode||'-')} • SN: ${esc(o.numeroSerie||'-')} • ${esc(o.statut||'')}</div>
              <div class="row" style="margin-top:6px">
                <button class="btn" data-act="open" data-id="${o.id}">Ouvrir</button>
                <button class="btn btn-danger" data-act="del" data-id="${o.id}">Supprimer</button>
              </div>
            </div>
          </label>`;
          row.addEventListener('click', e=>{
            const act=e.target.getAttribute('data-act'); if(!act) return;
            if(act==='open') openTool(o.id);
            if(act==='del'){ if(confirm('Supprimer ?')){ pushUndo(); model.outils=model.outils.filter(x=>x.id!==o.id); save(); renderResults(); histDiv.innerHTML=''; toast('Supprimé'); } }
          });
          resDiv.appendChild(row);
        });
        resCount.textContent=list.length+' résultats';
      }

      function updateLock(o){
        const locked=o.statut==='Clôturé';
        const fields=['nom','numeroSerie','qrCode','conseiller','categorie','collaborateur','dateAttribution','infos','observations'];
        fields.forEach(k=> inputs[k].disabled = locked);
        $('#btnSave').classList.toggle('lock', locked);
      }

      function openTool(id){
        const o=model.outils.find(x=>x.id===id); if(!o) return;
        selTool.value=id;
        inputs.nom.value=o.nom||''; inputs.numeroSerie.value=o.numeroSerie||''; inputs.qrCode.value=o.qrCode||'';
        inputs.conseiller.value=o.conseiller||''; inputs.categorie.value=o.categorie||''; inputs.collaborateur.value=o.collaborateur||'';
        inputs.statut.value=o.statut||'En service'; inputs.dateAttribution.value=o.dateAttribution||''; inputs.dateRetour.value=o.dateRetour||'';
        inputs.infos.value=o.infos||''; inputs.observations.value=o.observations||'';
        inputs.photoPrev.src=o.photoData||''; inputs.photoPrev.style.display=o.photoData?'block':'none';
        updateLock(o); renderHist(o);
      }

      function addHist(o,action,details){ o.historique=o.historique||[]; o.historique.unshift({date:new Date().toISOString(),action,details}); }
      function renderHist(o){ histDiv.innerHTML=''; (o.historique||[]).forEach(h=>{ const d=document.createElement('div'); d.style.cssText='border:1px solid var(--border);border-radius:10px;padding:8px'; d.innerHTML=`<div class="tag">${new Date(h.date).toLocaleString()}</div><div><strong>${esc(h.action)}</strong></div>${h.details?`<div>${esc(h.details)}</div>`:''}`; histDiv.appendChild(d); }); }

      function pushUndo(){ undoStack.push(JSON.stringify(model)); if(undoStack.length>20) undoStack.shift(); }
      $('#btnUndo').onclick=()=>{ if(!undoStack.length){ toast('Rien à annuler'); return } model=Object.assign(defaults(), JSON.parse(undoStack.pop())); save(); renderAll(); toast('Annulé'); };

      $('#btnCreate').onclick=()=>{ pushUndo(); const o={id:uid(),nom:'',qrCode:'',categorie:'',numeroSerie:'',collaborateur:'',conseiller:'',statut:'En service',dateAttribution:todayISO(),dateRetour:'',infos:'',observations:'',photoData:'',historique:[]}; addHist(o,'Création',''); model.outils.unshift(o); save(); refreshSelectors(); renderResults(); openTool(o.id); toast('Créé'); };
      $('#btnDup').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} pushUndo(); const n=JSON.parse(JSON.stringify(o)); n.id=uid(); n.nom=(o.nom||'')+' (copie)'; addHist(n,'Duplication','Depuis '+(o.nom||o.id)); model.outils.unshift(n); save(); renderResults(); openTool(n.id); toast('Dupliqué'); };
      $('#btnSave').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return}
        const p={ nom:inputs.nom.value.trim(), numeroSerie:inputs.numeroSerie.value.trim(), qrCode:inputs.qrCode.value.trim(), conseiller:inputs.conseiller.value, categorie:inputs.categorie.value, collaborateur:inputs.collaborateur.value, statut:inputs.statut.value, dateAttribution:inputs.dateAttribution.value, dateRetour:inputs.dateRetour.value, infos:inputs.infos.value, observations:inputs.observations.value };
        if(p.qrCode && model.outils.some(x=>x.qrCode===p.qrCode && x.id!==o.id)){ toast('QR déjà utilisé'); return }
        if(p.numeroSerie && model.outils.some(x=>x.numeroSerie===p.numeroSerie && x.id!==o.id)){ toast('N° série déjà utilisé'); return }
        pushUndo(); Object.assign(o,p); addHist(o,'Enregistrement',''); save(); renderResults(); openTool(o.id); toast('Enregistré'); };
      $('#btnDelete').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} if(confirm('Supprimer ?')){ pushUndo(); model.outils=model.outils.filter(x=>x.id!==o.id); save(); renderResults(); histDiv.innerHTML=''; toast('Supprimé'); } };
      $('#btnFindQR').onclick=()=>{ const q=inputs.qrCode.value.trim(); if(!q){toast('QR vide');return} const f=model.outils.find(x=>x.qrCode===q); if(f){ openTool(f.id); toast('Fiche ouverte'); } else toast('Aucune fiche'); };

      // clôturer = libérer QR et N° série
      $('#btnCloseReassign').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return}
        pushUndo(); const prevSN=o.numeroSerie||'-', prevQR=o.qrCode||'-'; o.statut='Clôturé'; o.dateRetour=todayISO(); addHist(o,'Clôture',`Libéré SN: ${prevSN} • QR: ${prevQR}`); o.qrCode=''; o.numeroSerie=''; save(); renderResults(); openTool(o.id); toast('Clôturé & libéré'); };
      $('#btnUnlock').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o) return; o.statut='En service'; addHist(o,'Déverrouillage',''); save(); openTool(o.id); toast('Déverrouillé'); };

      // calendrier icônes
      const openPicker=(i)=> i && (i.showPicker ? i.showPicker() : i.focus()); $('#iconAtt').onclick=()=>openPicker(inputs.dateAttribution); $('#iconRet').onclick=()=>openPicker(inputs.dateRetour);

      // Historique
      $('#btnAddHist').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} pushUndo(); addHist(o, $('#histAction').value, ($('#histDetail').value||'').trim()); save(); renderHist(o); $('#histDetail').value=''; };

      // Exports
      $('#btnExportCSV').onclick=()=>{ const rows=model.outils.map(o=>({id:o.id,Nom:o.nom||'',QR:o.qrCode||'',Categorie:o.categorie||'',NumeroSerie:o.numeroSerie||'',Collaborateur:o.collaborateur||'',Conseiller:o.conseiller||'',Statut:o.statut||'',DateAttribution:o.dateAttribution||'',DateRetour:o.dateRetour||'',Infos:o.infos||'',Observations:o.observations||''})); if(!rows.length){toast('Aucune donnée');return}
        const headers=Object.keys(rows[0]); const csv=[headers.join(',')].concat(rows.map(r=>headers.map(h=>String(r[h]).replace(/"/g,'""')).map(s=>(/[",\n]/.test(s)? '"'+s+'"' : s)).join(','))).join('\n'); download('outils.csv',csv,'text/csv;charset=utf-8;'); };
      $('#btnExportHistGlobal').onclick=()=>{ const rows=[]; model.outils.forEach(o=> (o.historique||[]).forEach(h=> rows.push({Outil:o.nom||o.qrCode||o.numeroSerie||o.id,Date:h.date,Action:h.action,Details:h.details||''}))); if(!rows.length){toast('Aucun historique');return}
        const headers=Object.keys(rows[0]); const csv=[headers.join(',')].concat(rows.map(r=>headers.map(h=>String(r[h]).replace(/"/g,'""')).map(s=>(/[",\n]/.test(s)? '"'+s+'"' : s)).join(','))).join('\n'); download('historique_global.csv',csv,'text/csv;charset=utf-8;'); };
      $('#btnExportHistTool').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return}
        const rows=(o.historique||[]).map(h=>({Outil:o.nom||o.qrCode||o.numeroSerie||o.id,Date:h.date,Action:h.action,Details:h.details||''})); if(!rows.length){toast('Aucun historique');return}
        const headers=Object.keys(rows[0]); const csv=[headers.join(',')].concat(rows.map(r=>headers.map(h=>String(r[h]).replace(/"/g,'""')).map(s=>(/[",\n]/.test(s)? '"'+s+'"' : s)).join(','))).join('\n'); download('historique_'+(o.nom||o.qrCode||o.numeroSerie||o.id).replace(/[^a-z0-9_-]+/gi,'_')+'.csv',csv,'text/csv;charset=utf-8;'); };

      // Imprimer & PDF
      function pageFiche(o){return `<!doctype html><meta charset=utf-8><style>body{font-family:system-ui;padding:20px} img{max-width:200px;max-height:200px}</style>
        <h1>Fiche outil</h1>
        ${o.photoData?`<p><img src="${o.photoData}"/></p>`:''}
        <p><b>Nom:</b> ${esc(o.nom||'')}</p>
        <p><b>QR:</b> ${esc(o.qrCode||'')}</p>
        <p><b>Catégorie:</b> ${esc(o.categorie||'')}</p>
        <p><b>SN:</b> ${esc(o.numeroSerie||'')}</p>
        <p><b>Collaborateur:</b> ${esc(o.collaborateur||'')}</p>
        <p><b>Conseiller:</b> ${esc(o.conseiller||'')}</p>
        <p><b>Statut:</b> ${esc(o.statut||'')}</p>
        <p><b>Date attribution:</b> ${esc(o.dateAttribution||'')}</p>
        <p><b>Date retour:</b> ${esc(o.dateRetour||'')}</p>`}
      $('#btnPrint').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} const w=window.open('','_blank'); w.document.write(pageFiche(o)); w.document.close(); };
      $('#btnPDF').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} const w=window.open('','_blank'); w.document.write(pageFiche(o)+"<script>setTimeout(()=>window.print(),300)<\/script>"); w.document.close(); };
      function pageHist(o){return `<!doctype html><meta charset=utf-8><style>body{font-family:system-ui;padding:20px}</style><h1>Historique</h1>${(o.historique||[]).map(h=>`<div><b>${new Date(h.date).toLocaleString()}</b> — ${esc(h.action)} — ${esc(h.details||'')}</div>`).join('')||'<p>Vide</p>'}`}
      $('#btnPrintHist').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} const w=window.open('','_blank'); w.document.write(pageHist(o)); w.document.close(); };
      $('#btnPDFHist').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} const w=window.open('','_blank'); w.document.write(pageHist(o)+"<script>setTimeout(()=>window.print(),300)<\/script>"); w.document.close(); };

      // Recherche / Reset
      $('#btnSearch').onclick=renderResults; $('#btnReset').onclick=()=>{ filters.q.value=''; filters.fCat.value=''; filters.fStat.value=''; filters.fCol.value=''; filters.fCon.value=''; renderResults(); };
      filters.q.addEventListener('keydown',e=>{ if(e.key==='Enter') renderResults(); });

      // Bulk
      $('#btnSelectAll').onclick=()=> $$('#results input[type=checkbox]').forEach(cb=> cb.checked=true);
      $('#btnBulkDelete').onclick=()=>{ const ids=$$('#results input[type=checkbox]:checked').map(cb=>cb.getAttribute('data-id')||cb.dataset.id); if(!ids.length){toast('Rien de sélectionné');return} if(confirm('Supprimer '+ids.length+' élément(s) ?')){ pushUndo(); model.outils=model.outils.filter(o=>!ids.includes(o.id)); save(); renderResults(); toast('Suppression groupée'); } };

      // QR live/photo
      async function scanLive(){ try{ if('BarcodeDetector' in window){ const detector=new BarcodeDetector({formats:['qr_code']}); const stream=await navigator.mediaDevices.getUserMedia({video:{facingMode:{ideal:'environment'}}}); const video=document.createElement('video'); video.setAttribute('playsinline',''); video.srcObject=stream; await video.play(); const canvas=document.createElement('canvas'); const ctx=canvas.getContext('2d'); let tries=0; const tick=()=>{ if(video.readyState>=2){ canvas.width=video.videoWidth; canvas.height=video.videoHeight; ctx.drawImage(video,0,0); } detector.detect(canvas).then(codes=>{ if(codes.length){ inputs.qrCode.value=codes[0].rawValue; stream.getTracks().forEach(t=>t.stop()); toast('QR détecté'); } else if(tries++<200) requestAnimationFrame(tick); else stream.getTracks().forEach(t=>t.stop()); }).catch(()=>{ stream.getTracks().forEach(t=>t.stop()); toast('Détection impossible'); }); }; tick(); } else { toast('Scanner non supporté (iOS 17+ requis)'); } }catch(e){ toast('Accès caméra refusé'); } }
      $('#btnScanLive').onclick=scanLive; $('#qrPhoto').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; inputs.qrCode.value=f.name; toast('Photo chargée'); this.value=''; });

      // Photo outil (base64)
      function fileToBase64(file, cb){ const r=new FileReader(); r.onload=e=>cb(e.target.result); r.readAsDataURL(file); }
      $('#photoInp').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; fileToBase64(f, b64=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o){toast('Sélectionne une fiche');return} o.photoData=b64; inputs.photoPrev.src=b64; inputs.photoPrev.style.display='block'; save(); toast('Photo ajoutée'); }); this.value=''; });
      $('#photoDel').onclick=()=>{ const o=model.outils.find(x=>x.id===selTool.value); if(!o) return; o.photoData=''; inputs.photoPrev.src=''; inputs.photoPrev.style.display='none'; save(); };

      // Modale listes
      const modal=$('#modal'), overlay=$('#overlay'); function openModal(){ modal.classList.add('show'); renderC(); renderS(); renderCat(); } function closeModal(){ modal.classList.remove('show') }
      $('#btnLists').onclick=openModal; overlay.onclick=closeModal; $('#btnCloseModal').onclick=closeModal;
      $$('[data-tab]').forEach(b=> b.addEventListener('click',()=>{ $('#tab-collabs').style.display = b.dataset.tab==='collabs' ? '' : 'none'; $('#tab-cons').style.display = b.dataset.tab==='cons' ? '' : 'none'; $('#tab-cats').style.display = b.dataset.tab==='cats' ? '' : 'none'; }));

      function readText(file, cb){ const r=new FileReader(); r.onload=e=>cb(e.target.result); r.readAsText(file,'utf-8') }
      function exportArrayCSV(name, rows, headers){ if(!rows.length){toast('Rien à exporter');return} const csv=[headers.join(',')].concat(rows.map(r=>headers.map(h=>String(r[h]||'').replace(/"/g,'""')).map(s=>(/[",\n]/.test(s)? '"'+s+'"' : s)).join(','))).join('\n'); download(name,csv,'text/csv;charset=utf-8;'); }

      // Collaborateurs (structuré id/first/last)
      const cBody=$('#cTable tbody');
      function renderC(){ cBody.innerHTML=''; model.collaborateurs.forEach((c,i)=>{ const tr=document.createElement('tr'); const id=c.id||''; const first=c.first||''; const last=c.last||''; tr.innerHTML=`<td><input type="checkbox" data-i="${i}"></td><td>${esc(id)}</td><td>${esc(first)}</td><td>${esc(last)}</td>`; cBody.appendChild(tr); }); refreshSelectors(); }
      $('#cAdd').onclick=()=>{ const id=$('#cId').value.trim(), first=$('#cFirst').value.trim(), last=$('#cLast').value.trim(); if(!id&&!first&&!last){toast('Renseigne au moins un champ');return} model.collaborateurs.push({id,first,last}); save(); renderC(); $('#cId').value=$('#cFirst').value=$('#cLast').value=''; };
      $('#cDel').onclick=()=>{ const ids=$$('#cTable tbody input[type=checkbox]:checked').map(cb=>parseInt(cb.dataset.i,10)).sort((a,b)=>b-a); if(!ids.length){toast('Sélectionne des lignes');return} ids.forEach(i=>model.collaborateurs.splice(i,1)); save(); renderC(); };
      $('#cAll').onchange=()=> $$('#cTable tbody input[type=checkbox]').forEach(cb=> cb.checked=$('#cAll').checked);
      // CSV: colonnes attendues: id,first,last (ou ID;prenom;nom)
      $('#cCSV').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; readText(f, t=>{ parseCSV(t).forEach(r=>{ const id=r.id||r.ID||r.numero||r.num||''; const first=r.first||r.prenom||r.Prénom||''; const last=r.last||r.nom||r.Nom||''; if(id||first||last) model.collaborateurs.push({id,first,last}); }); save(); renderC(); this.value=''; }); });
      $('#cExport').onclick=()=> exportArrayCSV('collaborateurs.csv', model.collaborateurs, ['id','first','last']);
      $('#cExportJSON').onclick=()=> download('collaborateurs.json', JSON.stringify(model.collaborateurs, null, 2), 'application/json');
      $('#cJSON').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; readText(f, t=>{ try{ const arr=JSON.parse(t); if(Array.isArray(arr)){ // accepte [{id,first,last}] ou "8176 — Maroine — ABDOU"
            arr.forEach(x=>{ if(typeof x==='string'){ const parts=x.split(/\s*—\s*|,|;|\|/); model.collaborateurs.push({id:parts[0]||'', first:parts[1]||'', last:parts[2]||''}); }
                               else model.collaborateurs.push({id:x.id||'', first:x.first||'', last:x.last||''}); });
            save(); renderC(); toast('Import JSON ok'); }
        }catch(e){ toast('JSON invalide'); } this.value=''; }); });

      // Conseillers
      const sBody=$('#sTable tbody');
      function renderS(){ sBody.innerHTML=''; model.conseillers.forEach((v,i)=>{ const tr=document.createElement('tr'); tr.innerHTML=`<td><input type="checkbox" data-i="${i}"></td><td>${esc(v)}</td>`; sBody.appendChild(tr); }); refreshSelectors(); }
      $('#sAdd').onclick=()=>{ const v=$('#sName').value.trim(); if(!v){ toast('Nom requis'); return } model.conseillers.push(v); save(); renderS(); $('#sName').value=''; };
      $('#sDel').onclick=()=>{ const ids=$$('#sTable tbody input[type=checkbox]:checked').map(cb=>parseInt(cb.dataset.i,10)).sort((a,b)=>b-a); if(!ids.length){ toast('Sélectionne des lignes'); return } ids.forEach(i=>model.conseillers.splice(i,1)); save(); renderS(); };
      $('#sAll').onchange=()=> $$('#sTable tbody input[type=checkbox]').forEach(cb=> cb.checked=$('#sAll').checked);
      $('#sCSV').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; readText(f, t=>{ parseCSV(t).forEach(r=>{ const v=r.conseiller||r.name||r.Nom||r.nom||''; if(v) model.conseillers.push(v) }); save(); renderS(); this.value=''; }); });
      $('#sExport').onclick=()=> exportArrayCSV('conseillers.csv', model.conseillers.map(v=>({conseiller:v})), ['conseiller']);
      $('#sExportJSON').onclick=()=> download('conseillers.json', JSON.stringify(model.conseillers, null, 2), 'application/json');
      $('#sJSON').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; readText(f, t=>{ try{ const arr=JSON.parse(t); if(Array.isArray(arr)){ model.conseillers=arr.map(v=>String(v)); save(); renderS(); toast('Import JSON ok'); } }catch(e){ toast('JSON invalide'); } this.value=''; }); });

      // Catégories
      const catBody=$('#catTable tbody');
      function renderCat(){ catBody.innerHTML=''; model.categories.forEach((v,i)=>{ const tr=document.createElement('tr'); tr.innerHTML=`<td><input type="checkbox" data-i="${i}"></td><td>${esc(v)}</td>`; catBody.appendChild(tr); }); refreshSelectors(); }
      $('#catAdd').onclick=()=>{ const v=$('#catName').value.trim(); if(!v){ toast('Nom requis'); return } model.categories.push(v); save(); renderCat(); $('#catName').value=''; };
      $('#catDel').onclick=()=>{ const ids=$$('#catTable tbody input[type=checkbox]:checked').map(cb=>parseInt(cb.dataset.i,10)).sort((a,b)=>b-a); if(!ids.length){ toast('Sélectionne des lignes'); return } ids.forEach(i=>model.categories.splice(i,1)); save(); renderCat(); };
      $('#catAll').onchange=()=> $$('#catTable tbody input[type=checkbox]').forEach(cb=> cb.checked=$('#catAll').checked);
      $('#catCSV').addEventListener('change', function(){ const f=this.files[0]; if(!f) return; readText(f, t=>{ parseCSV(t).forEach(r=>{ const v=r.categorie||r.category||r.nom||r.Nom||''; if(v) model.categories.push(v) }); save(); renderCat(); this.value=''; }); });
      $('#catExport').onclick=()=> exportArrayCSV('categories.csv', model.categories.map(v=>({categorie:v})), ['categorie']);
      $('#catExportJSON').onclick=()=> download('categories.json', JSON.stringify(model.categories, null, 2), 'application/json');

      // Rendu & init
      function renderAll(){ refreshSelectors(); renderResults(); if(selTool.value) openTool(selTool.value); }
      renderAll(); inputs.statut.value='En service'; jsState.textContent='OK'; jsState.style.color='#4ade80';
      setInterval(()=>{ backup(); save(); }, 30000);
      const offEl=document.getElementById('offline'); function updNet(){ offEl.textContent = navigator.onLine ? 'Online' : 'Offline'; offEl.style.color = navigator.onLine ? '#4ade80' : '#fca5a5'; } window.addEventListener('online',updNet); window.addEventListener('offline',updNet); updNet();
      window.addEventListener('keydown', e=>{ if(e.altKey && e.key.toLowerCase()==='r'){ restore(); } });

      // Recherche live
      ['change','input'].forEach(ev=>{ ['#fCat','#fStat','#fCol','#fCon','#q'].forEach(sel=> $(sel).addEventListener(ev, ()=>renderResults())); });

    }catch(e){ jsState.textContent='ERREUR'; document.getElementById('status').classList.add('err'); const pre=document.createElement('pre'); pre.textContent='Erreur : '+(e && e.message ? e.message : String(e)); pre.style.cssText='white-space:pre-wrap;background:#260e0e;color:#ffd9d9;padding:10px;border-radius:10px;border:1px solid #5a2b2b;margin:10px'; document.body.prepend(pre); }
  }
})();
</script>
</body>
</html>
