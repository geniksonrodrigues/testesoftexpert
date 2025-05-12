
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Simulador de E-mail - Genikson</title>
    <style>
      * {
        box-sizing: border-box;
      }
      body {
        margin: 0;
        font-family: "Segoe UI", sans-serif;
        background: #f0f2f5;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
      }
      .container {
        background: white;
        width: 100%;
        max-width: 1200px;
        border: 1px solid #ccc;
        border-radius: 12px;
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
        overflow: hidden;
      }
      .header {
        background: linear-gradient(135deg, #ff416c, #ff4b2b);
        color: white;
        padding: 1rem;
        font-size: 1.3rem;
        font-weight: bold;
        text-align: center;
      }
      .content {
        padding: 1.5rem;
        line-height: 1.7;
      }
      .content a {
        color: #ff4b2b;
        text-decoration: underline;
      }
      .button-area {
        display: flex;
        justify-content: space-between;
        padding: 1rem 1.5rem;
        background-color: #fafafa;
      }
      .button {
        background: linear-gradient(135deg, #ff416c, #ff4b2b);
        color: white;
        border: none;
        padding: 0.5rem 1rem;
        font-size: 1rem;
        border-radius: 8px;
        cursor: pointer;
        transition: background 0.3s;
      }
      .button:hover {
        background: linear-gradient(135deg, #e63e62, #e2451f);
      }
    </style>
  </head>
  <body>
    <div class="container" id="mainMenu">
      <div class="header">Desafio - Pessoa Técnica de Suporte</div>
      <div class="content" style="text-align: center">
        <button class="button" onclick="showPage('page1')">Cenário e Resposta ao Cliente</button>
        <button class="button" onclick="showPage('diagnostico')">
          Diagnóstico e Próximos Passos
        </button>
        <button class="button" onclick="showPage('registro')">Documentação Interna</button>
      </div>
    </div>

    <div class="container" id="page1" style="display: none">
      <div class="header">📩 E-mail Recebido</div>
      <div class="content">
        Oi, tudo bem? Desde ontem à tarde, quando tento acessar o sistema,
        aparece uma tela em branco. Já tentei atualizar a página e trocar de
        navegador, mas nada funciona. Preciso disso para trabalhar, vocês
        conseguem me ajudar com urgência?
      </div>
      <div class="button-area">
        <button class="button" onclick="goToResponse()">
          Avançar para resposta
        </button>
      </div>
    </div>

    <div class="container" id="page2" style="display: none">
      <div class="header">📤 Resposta de Genikson</div>
      <div class="content" id="resposta"></div>
      <div class="button-area">
        <button class="button" onclick="window.location.reload()">
          Voltar ao início
        </button>
      </div>
    </div>

    <div class="container" id="diagnostico" style="display: none">
      <div class="header">🔍 Diagnóstico e próximos passos</div>
      <div class="content">
        <p>
          <strong>1. Consulta ao histórico de ocorrências:</strong><br />
          Verificar na base de conhecimento e registros anteriores se já houve
          chamados similares (como "tela em branco") e quais foram as soluções
          bem-sucedidas.
        </p>

        <p>
          <strong>2. Coleta de informações com o cliente:</strong><br />
          Solicitar retorno com evidências como print da tela, link de acesso e
          testes já realizados, a fim de obter dados precisos.
        </p>

        <p>
          <strong>3. Análise técnica inicial:</strong><br />
          Analisar as evidências para identificar se há solução imediata com
          base no padrão de funcionamento do sistema ou nos casos registrados
          anteriormente.
        </p>

        <p>
          <strong>4. Escalonamento ao time de TI (caso necessário):</strong
          ><br />
          Se a análise não indicar solução imediata, abrir chamado ao time de TI
          com os detalhes do caso, anexando evidências e nível de urgência.
        </p>

        <p>
          <strong>5. Comunicação com o cliente:</strong><br />
          Enviar novo e-mail explicando que o caso foi escalado, sem usar termos
          técnicos, e informando prazo estimado de resposta.
        </p>

        <p>
          <strong>6. Priorização (em caso crítico):</strong><br />
          Se a falha estiver impactando atividades críticas, acionar liderança
          para avaliar priorização do chamado junto ao TI.
        </p>

        <p>
          <strong>7. Retorno ao cliente com solução ou encaminhamento:</strong
          ><br />
          Após resposta do TI, entrar em contato com o cliente explicando a
          solução em linguagem acessível, confirmando retorno do funcionamento
          antes de encerrar o ticket.
        </p>
      </div>
      <div class="button-area">
        <button class="button" onclick="window.location.reload()">
          Voltar ao início
        </button>
      </div>
    </div>

    <div class="container" id="registro" style="display: none">
      <div class="header">📝 Registro do atendimento</div>
      <div class="content">
        <p>
          <strong
            >Como eu registraria esse atendimento no sistema interno da
            empresa:</strong
          >
        </p>
        <p>
          Manteria o ticket aberto ou com o status "Aguardando retorno do time
          de Produto/TI", evitando o encerramento prematuro. Isso garante que o
          cliente possa responder ao mesmo chamado e que outros colegas
          identifiquem facilmente que o atendimento ainda está em andamento,
          evitando retrabalho ou perda de histórico.
        </p>

        <p>
          Em seguida, documentaria de forma clara e objetiva as seguintes
          informações no corpo do ticket:
        </p>
        <ul>
          <li>Número do chamado aberto junto ao TI;</li>
          <li>Nome do responsável técnico pelo caso (caso haja);</li>
          <li>
            Descrição resumida das tratativas já realizadas com o cliente;
          </li>
          <li>Última atualização e etapa atual do atendimento.</li>
        </ul>

        <p>
          Caso eu estivesse ausente e os registros de e-mail não estivessem
          integrados ao sistema de chamados, anexaria uma cópia da troca de
          mensagens com o cliente, nomeando o arquivo como “Histórico de E-mails
          com o Cliente – [Data]”, garantindo que qualquer colega possa dar
          continuidade ao atendimento com total contexto.
        </p>

        <p>
          Dessa forma, asseguro a rastreabilidade, transparência e continuidade
          do atendimento mesmo em caso de repasse.
        </p>
      </div>
      <div class="button-area">
        <button class="button" onclick="window.location.reload()">
          Voltar ao início
        </button>
      </div>
    </div>

    <script>
      const partes = [
        `Olá, Ana! Bom dia, tudo bem?`,
        `Sinto muito pela dificuldade que você está enfrentando e entendo como isso pode impactar diretamente o seu trabalho. Estou aqui para te ajudar a resolver essa situação o mais rápido possível! 😉`,
        `Esse comportamento (tela em branco) pode estar relacionado a um problema temporário de cache ou a uma instabilidade pontual em algum módulo do sistema. Vamos seguir juntos com algumas etapas rápidas para tentar resolver:`,
        `1. Acesse o sistema em modo anônimo:<br> Clique em Ctrl+Shift+N (ou use o menu do seu navegador) para abrir uma aba anônima e, em seguida, tente acessar o sistema normalmente.`,
        `2. Caso funcione no modo anônimo:<br> Feche a aba anônima, volte ao navegador principal e siga este passo a passo para limpar cache e cookies:<br><a href="https://support.google.com/accounts/answer/32050" target="_blank">Google Chrome: Como limpar cache e cookies</a><br><a href="https://support.microsoft.com/pt-br/microsoft-edge/excluir-o-hist%C3%B3rico-de-navega%C3%A7%C3%A3o-no-microsoft-edge-14b6e63b-1124-8f56-6c27-4f4db9233187" target="_blank">Microsoft Edge: Gerenciar cookies no Edge</a>`,
        `3. Se o problema persistir:<br>Nos envie, por gentileza:<br>- Um print da tela em branco (atalho: Windows + Shift + S);<br>- O link da página em que o erro aparece (mesmo que seja o link da tela inicial).`,
        `Com essas informações, conseguiremos investigar com mais precisão e agilidade.`,
        `Se preferir, também posso te ajudar por chamada de voz ou via Teams para realizar esses passos juntos. Basta me avisar!`,
        `Estou à disposição e acompanhando de perto para garantir que você volte a acessar o sistema o quanto antes.`,
        `Atenciosamente,<br><strong>Genikson<br>Suporte Técnico SoftExpert</strong>`,
      ]

      function showPage(pageId) {
        document
          .querySelectorAll(".container")
          .forEach((el) => (el.style.display = "none"))
        document.getElementById(pageId).style.display = "block"
      }

      function goToResponse() {
        document.getElementById("page1").style.display = "none"
        document.getElementById("page2").style.display = "block"
        typeParagraphs(partes, "resposta")
      }

      function typeParagraphs(paragraphs, elementId, speed = 20) {
        const element = document.getElementById(elementId)
        element.innerHTML = ""
        let i = 0

        function typeParagraph() {
          if (i >= paragraphs.length) return
          const p = document.createElement("p")
          p.innerHTML = ""
          element.appendChild(p)

          let j = 0
          const currentText = paragraphs[i]

          function typeChar() {
            if (j < currentText.length) {
              const char = currentText[j]
              if (char === "<") {
                const closeIndex = currentText.indexOf(">", j)
                p.innerHTML += currentText.slice(j, closeIndex + 1)
                j = closeIndex + 1
              } else {
                p.innerHTML += char
                j++
              }
              setTimeout(typeChar, speed)
            } else {
              i++
              setTimeout(typeParagraph, 400)
            }
          }

          typeChar()
        }

        typeParagraph()
      }
    </script>
  </body>
</html>
