<doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Cadastro</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; max-width: 480px; margin: auto; }
    label { display:block; margin-top:12px; font-weight:600; }
    input { width:100%; padding:8px; margin-top:6px; box-sizing:border-box; }
    .error { color:#c00; font-size:0.9em; }
    button { margin-top:14px; padding:10px 16px; border:none; border-radius:6px; cursor:pointer; }
  </style>
</head>
<body>
  <h1>Cadastre-se</h1>
  <p>Preencha nome, telefone e e-mail</p>

  <form id="myForm" method="POST" action="">
    <label for="name">Nome</label>
    <input id="name" name="name" type="text" required />

    <label for="phone">Telefone</label>
    <input id="phone" name="phone" type="tel" pattern="[\d+\-\s()]{6,}" required />

    <label for="email">E-mail</label>
    <input id="email" name="email" type="email" required />

    <div id="msg" class="error" role="alert" aria-live="polite"></div>

    <button type="submit">Enviar</button>
  </form>

  <script>
    const form = document.getElementById('myForm');
    const msg = document.getElementById('msg');

    form.addEventListener('submit', async (e) => {
      e.preventDefault();
      msg.textContent = '';

      const formData = new FormData(form);
      const action = form.getAttribute('action') || window.location.href;

      try {
        const res = await fetch(action, {
          method: 'POST',
          body: formData,
          headers: { 'Accept': 'application/json' }
        });

        if (res.ok) {
          form.reset();
          msg.style.color = 'green';
          msg.textContent = 'Enviado com sucesso — obrigado!';
        } else {
          const data = await res.json().catch(()=>null);
          msg.style.color = '#c00';
          msg.textContent = data?.error || 'O envio falhou. Tente novamente.';
        }
      } catch (err) {
        msg.style.color = '#c00';
        msg.textContent = 'Erro de rede. Verifique sua conexão.';
        console.error(err);
      }
    });
  </script>
</body>
</html>
