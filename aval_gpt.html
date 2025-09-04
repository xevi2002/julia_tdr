<!DOCTYPE html>
<html lang="ca">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Avaluació de Salut i Envelliment</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    .input { width: 100%; border: 1px solid #d1d5db; border-radius: 0.75rem; padding: 0.5rem 0.75rem; }
    .input:focus { outline: none; border-color: #2563eb; box-shadow: 0 0 0 2px #2563eb33; }
  </style>
</head>
<body class="bg-gray-50 text-gray-900">
  <div class="max-w-5xl mx-auto p-6">
    <header class="mb-6">
      <h1 class="text-3xl font-bold">Avaluació de Salut i Envelliment</h1>
      <p class="text-sm text-gray-600 mt-2">Aquesta eina recull les teves respostes i calcula una puntuació de salut/benestar (0–100) i el risc d'envelliment accelerat. No és un diagnòstic mèdic.</p>
    </header>

    <div class="grid md:grid-cols-3 gap-6">
      <aside class="md:col-span-1">
        <div class="bg-white rounded-2xl shadow p-5 sticky top-4">
          <h2 class="text-xl font-semibold mb-3">Resultat</h2>
          <div class="mb-4">
            <div class="text-sm text-gray-600">Puntuació</div>
            <div id="score" class="text-5xl font-extrabold">—</div>
          </div>
          <div class="mb-2 flex items-center justify-between">
            <span class="text-sm text-gray-600">Nivell</span>
            <span id="nivell" class="text-sm font-semibold px-2 py-1 rounded-full bg-gray-100 text-gray-800">—</span>
          </div>
          <div class="mt-4 border-t pt-4">
            <div class="text-sm text-gray-600">Índex de massa corporal (IMC)</div>
            <div id="bmi" class="text-lg font-semibold">—</div>
          </div>
          <div id="tipsBox" class="hidden mt-4 border-t pt-4">
            <div class="text-sm font-semibold mb-2">Suggeriments personalitzats</div>
            <ul id="tipsList" class="list-disc ml-5 space-y-1 text-sm"></ul>
          </div>
          <div class="mt-6 flex gap-2">
            <button onclick="netejaForm()" class="px-3 py-2 rounded-xl bg-gray-100 hover:bg-gray-200 text-sm">Neteja</button>
            <button onclick="scrollToRecom()" class="px-3 py-2 rounded-xl bg-blue-600 hover:bg-blue-700 text-white text-sm">Vés a recomanacions</button>
          </div>
        </div>
      </aside>

      <main class="md:col-span-2">
        <section class="bg-white rounded-2xl shadow p-5 mb-6">
          <h2 class="text-lg font-semibold mb-4">Dades i hàbits</h2>
          <form id="formSalut" class="grid md:grid-cols-2 gap-4">
            <label class="flex flex-col gap-1">
              <span class="text-sm font-medium">Quants anys té actualment?</span>
              <input type="number" name="edat" min="0" max="110" class="input" />
            </label>
            <label class="flex flex-col gap-1">
              <span class="text-sm font-medium">Quantes hores diàries dorm?</span>
              <input type="number" name="horesDormir" min="0" max="24" step="0.5" class="input" />
            </label>
            <label class="flex flex-col gap-1">
              <span class="text-sm font-medium">Quant pesa en kg?</span>
              <input type="number" name="pes" min="0" max="300" step="0.1" class="input" />
            </label>
            <label class="flex flex-col gap-1">
              <span class="text-sm font-medium">Quina alçada té en cm?</span>
              <input type="number" name="alcada" min="0" max="260" class="input" />
            </label>
            <!-- Pots afegir aquí la resta de preguntes segons calgui -->
          </form>
          <button type="button" onclick="avaluar()" class="mt-4 px-4 py-2 rounded-xl bg-green-600 hover:bg-green-700 text-white">Calcula resultat</button>
        </section>

        <section id="recomanacions" class="bg-white rounded-2xl shadow p-5">
          <h2 class="text-lg font-semibold mb-3">Com interpretar el resultat</h2>
          <ul class="list-disc ml-5 space-y-1 text-sm text-gray-700">
            <li><strong>≥ 85</strong>: Salut excel·lent</li>
            <li><strong>70–84</strong>: Bona salut</li>
            <li><strong>55–69</strong>: Salut acceptable</li>
            <li><strong>40–54</strong>: Millorable</li>
            <li><strong>&lt; 40</strong>: Risc alt</li>
          </ul>
          <p class="mt-3 text-sm text-gray-600">La metodologia és heurística i orientativa. Per a assessoria personalitzada, consulta professionals de la salut.</p>
        </section>
      </main>
    </div>

    <footer class="mt-10 text-xs text-gray-500">
      Fet amb finalitats educatives. — © <span id="any"></span>
    </footer>
  </div>

  <script>
    document.getElementById("any").textContent = new Date().getFullYear();

    function clamp(v, a, b){ return Math.max(a, Math.min(b, v)); }
    function bmi(pes, alcada){ if(!pes||!alcada) return null; const h=alcada/100; if(h<=0) return null; return Math.round((pes/(h*h))*10)/10; }
    function categoriaBMI(b){ if(b==null) return "—"; if(b<18.5) return "Pes baix"; if(b<25) return "Normal"; if(b<30) return "Sobrepès"; if(b<35) return "Obesitat I"; if(b<40) return "Obesitat II"; return "Obesitat III"; }

    function calcula(){
      const f=new FormData(document.getElementById("formSalut"));
      let score=100; let tips=[];
      const edat=Number(f.get("edat"));
      if(edat){ if(edat>=75) score-=10; else if(edat>=60) score-=5; else if(edat>=20&&edat<=39) score+=5; }
      const hDormir=Number(f.get("horesDormir"));
      if(hDormir){ if(hDormir>=7&&hDormir<=9) score+=5; else if(hDormir<6){ score-=8; tips.push("Intenta dormir entre 7 i 9 hores."); } }
      const pes=Number(f.get("pes"));
      const alcada=Number(f.get("alcada"));
      const b=bmi(pes,alcada);
      if(b!=null){
        if(b<18.5){ score-=4; tips.push("Revisa la ingesta calòrica i proteica."); }
        else if(b<25){ score+=6; }
        else if(b<30){ score-=4; tips.push("Perdre una mica de pes podria ajudar."); }
        else if(b<35){ score-=8; tips.push("Consulta estratègies per reduir pes."); }
        else{ score-=12; tips.push("Risc elevat associat al pes."); }
      }
      score=clamp(Math.round(score),0,100);
      let nivell="Risc alt";
      if(score>=85) nivell="Salut excel·lent"; else if(score>=70) nivell="Bona salut"; else if(score>=55) nivell="Salut acceptable"; else if(score>=40) nivell="Millorable";
      return {score,bmi:b,bmiCat:categoriaBMI(b),nivell,tips:[...new Set(tips)]};
    }

    function avaluar(){
      const r=calcula();
      document.getElementById("score").textContent=r.score;
      document.getElementById("nivell").textContent=r.nivell;
      document.getElementById("bmi").textContent=r.bmi? r.bmi+" ("+r.bmiCat+")":"—";
      const box=document.getElementById("tipsBox");
      const list=document.getElementById("tipsList");
      if(r.tips.length){ box.classList.remove("hidden"); list.innerHTML=""; r.tips.forEach(t=>{const li=document.createElement("li"); li.textContent=t; list.appendChild(li);}); } else { box.classList.add("hidden"); }
    }

    function netejaForm(){
      document.getElementById("formSalut").reset();
      document.getElementById("score").textContent="—";
      document.getElementById("nivell").textContent="—";
      document.getElementById("bmi").textContent="—";
      document.getElementById("tipsBox").classList.add("hidden");
    }
    function scrollToRecom(){ document.getElementById("recomanacions").scrollIntoView({behavior:'smooth'}); }
  </script>
</body>
</html>
