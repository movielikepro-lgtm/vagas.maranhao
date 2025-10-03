<html lang="pt-BR">
<head>
<meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1">
<title>Vagas Maranhão — Anúncios e Currículos</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#10051f;      /* fundo base (roxo quase preto) */
    --bg2:#2a0f3f;     /* topo do gradiente */
    --card:#1b0c2c;    /* cartões */
    --border:#3a1a5a;  /* bordas */
    --text:#efe7ff;    /* texto principal */
    --muted:#bdb0d9;   /* texto secundário */
    --brand:#8a4bff;   /* roxo principal */
    --brand2:#c06cff;  /* roxo claro */
    --ok:#5ad9a6;      /* verde de confirmação */
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    background:linear-gradient(180deg,var(--bg2) 0%, var(--bg) 100%);
    color:var(--text);
    font-family:Inter,system-ui
  }
  a{color:#e1d4ff}
  .wrap{max-width:980px;margin:0 auto;padding:22px}
  header,footer{display:flex;align-items:center;justify-content:space-between;gap:12px}
  .brand{display:flex;gap:12px;align-items:center}
  .logo{
    width:44px;height:44px;border-radius:12px;
    background:radial-gradient(100% 100% at 100% 0, var(--brand2) 0, var(--brand) 45%, #2a0f3f 100%);
    box-shadow:0 10px 30px rgba(138,75,255,.35)
  }
  h1{font-size:22px;margin:0}
  .pill{
    background:#200a34;border:1px solid var(--border);
    padding:6px 10px;border-radius:999px;color:#d9c9ff
  }
  .card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:20px}
  .grid{display:grid;gap:16px}
  .cols2{grid-template-columns:1fr 1fr}
  .btn{
    display:inline-block;padding:14px 18px;border-radius:12px;
    border:1px solid var(--border);background:#240a3e;color:#fff;
    font-weight:700;text-decoration:none;cursor:pointer
  }
  .btn.primary{background:linear-gradient(180deg,var(--brand),#6a2dff);border:0}
  .btn.success{background:linear-gradient(180deg,#58e0b2,#2bb986);border:0}
  .btn.ghost{background:transparent}
  label{font-weight:600}
  input,select,textarea{
    width:100%;background:#1f0b34;border:1px solid var(--border);
    color:var(--text);padding:12px;border-radius:10px;outline:none
  }
  textarea{min-height:110px}
  .small{color:var(--muted);font-size:13px}
  .tag{
    display:inline-block;background:#1f0b34;border:1px solid var(--border);
    padding:6px 10px;border-radius:999px;color:#eadbff
  }
  .hidden{display:none}
  .nav{display:flex;gap:10px;flex-wrap:wrap}
  hr{border:0;border-top:1px solid var(--border);margin:12px 0}
</style>
</head>
<body>
<div class="wrap">
  <header>
    <div class="brand">
      <div class="logo"></div>
      <div>
        <h1>Vagas Maranhão</h1>
        <div class="pill">@vagasmaranhao_ • Instagram</div>
      </div>
    </div>
    <div class="nav">
      <a class="btn" href="https://instagram.com/vagasmaranhao_" target="_blank" rel="noopener">@vagasmaranhao_</a>
      <button class="btn success" onclick="go('curriculo')">Criar currículo</button>
    </div>
  </header>

  <!-- INÍCIO -->
  <section id="home" class="card">
    <h2>O que deseja fazer?</h2>
    <div class="grid">
      <div class="nav">
        <button class="btn primary" onclick="go('anuncio')">Divulgar vaga / anúncio</button>
        <button class="btn success" onclick="go('curriculo')">Criar currículo profissional</button>
      </div>
      <hr>
      <div class="small">Divulgação no Instagram (feed e stories), grupos no WhatsApp e canal no Telegram. Publicação após confirmação do pagamento. Permanência: Feed (indefinida), Stories (24h) e Grupos (90 dias).</div>
      <div class="nav">
        <span class="tag">Vaga por PIX: R$ 17,00</span>
        <span class="tag">Vaga no cartão: R$ 17,75</span>
        <span class="tag">Outros anúncios: R$ 50,00 (PIX) / R$ 50,20 (cartão)</span>
      </div>
      <div class="small">Contato: 98 99211‑9065 • E-mail: contatovagasma@gmail.com</div>
    </div>
  </section>

  <!-- ANÚNCIO -->
  <section id="anuncio" class="card hidden">
    <h2>Dados do anúncio</h2>
    <div class="grid cols2">
      <div>
        <label>Tipo</label>
        <select id="tipo">
          <option value="vaga">Vaga de emprego</option>
          <option value="outros">Outros anúncios</option>
        </select>
      </div>
      <div>
        <label>Forma de pagamento</label>
        <select id="forma">
          <option value="pix">PIX</option>
          <option value="cartao">Cartão</option>
        </select>
      </div>
      <div><label>Empresa</label><input id="empresa"></div>
      <div><label>CNPJ (opcional)</label><input id="cnpj"></div>
      <div><label>Contato (e-mail/telefone)</label><input id="contato"></div>
      <div><label>Cidade/UF</label><input id="local"></div>
      <div><label>Título</label><input id="titulo"></div>
      <div><label>Descrição/Requisitos</label><textarea id="descricao"></textarea></div>
      <div><label>Link (opcional)</label><input id="link"></div>
    </div>
    <hr>
    <div id="resumo" class="tag">Valores conforme tipo e forma de pagamento.</div>
    <div class="nav" style="margin-top:12px">
      <button class="btn" onclick="go('home')">Voltar</button>
      <button class="btn primary" onclick="goPagamento()">Ir para pagamento</button>
    </div>
  </section>

  <!-- PAGAMENTO -->
  <section id="pagamento" class="card hidden">
    <h2>Pagamento</h2>
    <div id="resPag" class="small" style="margin-bottom:10px"></div>
    <div class="grid cols2">
      <div>
        <label>Chave PIX</label>
        <div class="nav">
          <input id="pix" value="contatovagasma@gmail.com" readonly>
          <button class="btn" onclick="copy('#pix')">Copiar</button>
        </div>
        <div class="small">Titular: Bruno Silva Matos.</div>
        <div class="small" style="margin-top:6px">Após o pagamento, envie o comprovante e a arte pelo mesmo formulário oficial (link abaixo).</div>
      </div>
      <div class="card" style="background:#22093a;border-style:dashed">
        <div class="small"><b>Cartão:</b> Vaga R$ 17,75 • Outros R$ 50,20. Para aprovação mais rápida, preferir PIX.</div>
      </div>
    </div>
    <hr>
    <h3>Envio do comprovante e da arte</h3>
    <p class="small">Use o link a seguir para abrir o formulário em nova aba e anexar: 1) comprovante do pagamento e 2) arte da publicação (se houver).</p>
    <p>
      <a class="btn success" href="https://forms.gle/VHeC9W7y56eFkU1p9" target="_blank" rel="noopener">Abrir formulário de comprovante e arte</a>
    </p>
    <div class="nav" style="margin-top:12px">
      <button class="btn" onclick="go('anuncio')">Voltar</button>
      <button class="btn primary" onclick="go('sucesso')">Já enviei — abrir WhatsApp</button>
    </div>
  </section>

  <!-- SUCESSO / WHATSAPP -->
  <section id="sucesso" class="card hidden">
    <h2>Obrigado! Vamos confirmar o pagamento.</h2>
    <p class="small">A mensagem será aberta no WhatsApp com o resumo do anúncio e a frase “Enviei o comprovante via formulário e anexei a arte pelo mesmo link”.</p>
    <div class="nav">
      <a id="waAnuncio" class="btn primary" target="_blank" rel="noopener">Abrir WhatsApp (98 99211‑9065)</a>
      <button class="btn" onclick="go('home')">Voltar ao início</button>
    </div>
    <hr>
    <div class="small">Suporte: contatovagasma@gmail.com</div>
  </section>

  <!-- CURRÍCULO -->
  <section id="curriculo" class="card hidden">
    <h2>Criar currículo profissional</h2>
    <div class="grid cols2">
      <div><label>Nome completo</label><input id="cv_nome"></div>
      <div><label>WhatsApp</label><input id="cv_tel"></div>
      <div><label>E-mail</label><input id="cv_email"></div>
      <div><label>Cidade/UF</label><input id="cv_local"></div>
      <div><label>Cargo desejado</label><input id="cv_cargo"></div>
      <div><label>Pretensão (opcional)</label><input id="cv_sal"></div>
      <div class="cols2" style="grid-column:1/3;display:grid;gap:16px">
        <div><label>Resumo profissional</label><textarea id="cv_resumo"></textarea></div>
        <div><label>Habilidades</label><textarea id="cv_hab" placeholder="Excel, Atendimento, Vendas, CNH B..."></textarea></div>
        <div><label>Formação</label><textarea id="cv_form"></textarea></div>
        <div><label>Cursos/Certificações</label><textarea id="cv_cursos"></textarea></div>
        <div><label>Experiências recentes</label><textarea id="cv_exp"></textarea></div>
        <div><label>Disponibilidade</label><input id="cv_disp"></div>
        <div><label>Links (LinkedIn/Portfólio)</label><input id="cv_links"></div>
      </div>
    </div>
    <div class="nav" style="margin-top:12px">
      <button class="btn" onclick="go('home')">Voltar</button>
      <a id="waCV" class="btn success" target="_blank" rel="noopener">Enviar no WhatsApp (98 98782‑1271)</a>
    </div>
  </section>

  <footer class="small" style="margin-top:16px">
    <span>© Vagas Maranhão — Instagram: <a href="https://instagram.com/vagasmaranhao_" target="_blank" rel="noopener">@vagasmaranhao_</a></span>
    <span> • Comercial: 98 99211‑9065 • E-mail: contatovagasma@gmail.com</span>
  </footer>
</div>

<script>
  function go(id){
    document.querySelectorAll('section.card').forEach(s=>s.classList.add('hidden'));
    document.getElementById(id).classList.remove('hidden');
    window.scrollTo({top:0,behavior:'smooth'});
    if(id==='curriculo') buildCV();
    if(id==='sucesso') montarWhatsAppAnuncio();
  }
  const $=s=>document.querySelector(s);
  function copy(sel){ navigator.clipboard.writeText($(sel).value).then(()=>alert('Chave PIX copiada.')); }

  function price(tipo,forma){ return tipo==='vaga'?(forma==='pix'?17:17.75):(forma==='pix'?50:50.2); }
  const D = {tipo:'vaga', forma:'pix'};
  function updateResumo(){
    D.tipo = $('#tipo').value; D.forma = $('#forma').value;
    D.valor = price(D.tipo,D.forma);
    $('#resumo').textContent = `Resumo: ${D.tipo==='vaga'?'Vaga de emprego':'Outros anúncios'} • ${D.forma.toUpperCase()} • Total R$ ${D.valor.toFixed(2)}`;
  }
  ['tipo','forma'].forEach(id=>document.getElementById(id).addEventListener('change',updateResumo)); updateResumo();

  function goPagamento(){
    Object.assign(D,{
      empresa:$('#empresa').value.trim(), cnpj:$('#cnpj').value.trim(),
      contato:$('#contato').value.trim(), local:$('#local').value.trim(),
      titulo:$('#titulo').value.trim(), descricao:$('#descricao').value.trim(),
      link:$('#link').value.trim()
    });
    $('#resPag').textContent = `Pagamento de ${D.tipo==='vaga'?'Vaga de emprego':'Outros anúncios'} no valor de R$ ${D.valor.toFixed(2)} (${D.forma.toUpperCase()}).`;
    go('pagamento');
  }

  function montarWhatsAppAnuncio(){
    const linhas = [
      'Anúncio — Vagas Maranhão (@vagasmaranhao_)',
      `Tipo: ${D.tipo==='vaga'?'Vaga de emprego':'Outros anúncios'}`,
      `Empresa: ${D.empresa||'-'}`, D.cnpj?`CNPJ: ${D.cnpj}`:null,
      `Contato: ${D.contato||'-'} • E-mail: contatovagasma@gmail.com`,
      `Local: ${D.local||'-'}`, `Título: ${D.titulo||'-'}`,
      `Descrição/Requisitos: ${D.descricao||'-'}`, D.link?`Link: ${D.link}`:null,
      `Pagamento: ${D.forma.toUpperCase()} • Total R$ ${Number(D.valor||0).toFixed(2)}`,
      `Status: Enviei o comprovante via formulário e anexei a arte pelo mesmo link (https://forms.gle/VHeC9W7y56eFkU1p9).`
    ].filter(Boolean).join('\n');
    const wa = `https://wa.me/5598992119065?text=${encodeURIComponent(linhas)}`;
    $('#waAnuncio').href = wa;
  }

  function buildCV(){
    const v=id=>$(id).value.trim();
    const texto = [
      'Currículo — Vagas Maranhão (@vagasmaranhao_)',
      `Nome: ${v('#cv_nome')}`, `WhatsApp: ${v('#cv_tel')}`, `E-mail: ${v('#cv_email')}`, `Cidade/UF: ${v('#cv_local')}`,
      `Cargo desejado: ${v('#cv_cargo')}`, v('#cv_sal')?`Pretensão: ${v('#cv_sal')}`:null,
      `Resumo: ${v('#cv_resumo')}`, `Habilidades: ${v('#cv_hab')}`,
      `Formação: ${v('#cv_form')}`, v('#cv_cursos')?`Cursos/Certificações: ${v('#cv_cursos')}`:null,
      `Experiências: ${v('#cv_exp')}`, `Disponibilidade: ${v('#cv_disp')}`,
      v('#cv_links')?`Links: ${v('#cv_links')}`:null
    ].filter(Boolean).join('\n');
    $('#waCV').href = 'https://wa.me/5598987821271?text='+encodeURIComponent(texto);
  }
  document.querySelectorAll('#curriculo input,#curriculo textarea').forEach(el=>el.addEventListener('input',buildCV));

  go('home');
</script>
</body>
</html>
