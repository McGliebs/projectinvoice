# Gerador Faturas

Converte dados de faturação aérea e marítima em faturas de texto formatadas.
*Converts airline and ferry billing data into clean, formatted text invoices.*

**Formatos suportados / Supported formats**

| Formato | Origem / Source |
|---|---|
| **GDS Amadeus** | TAP / SATA — ecrã do bilhete guardado em PDF (voos directos e ligações) |
| **GDS / ETKT** | PDF do bilhete (`TKT_…`) — vários de uma vez |
| **EasyJet** | PDF de confirmação de pagamento |
| **Porto Santo Line** | PDF do bilhete de ferry (passageiros e viaturas) |

[![Última versão](https://img.shields.io/github/v/release/McGliebs/projectinvoice?label=vers%C3%A3o&color=0b5394)](https://github.com/McGliebs/projectinvoice/releases/latest)

---

<details open>
<summary><h2>🇵🇹 &nbsp;Português (PT-PT)</h2></summary>

### Instalação

1. Vá à [versão mais recente](https://github.com/McGliebs/projectinvoice/releases/latest).
2. Descarregue o **`GeradorFaturas.exe`**.
3. Execute — não precisa de instalação.

Na primeira execução o Windows pode mostrar um aviso do SmartScreen (aplicação
sem assinatura digital): clique em **Mais informações → Executar mesmo assim**.

> A aplicação procura atualizações automaticamente ao arrancar. Quando existe
> uma versão mais recente, propõe descarregar e instalar; depois reinicia-se
> sozinha.

### Utilização — PDF (GDS / ETKT, EasyJet, Porto Santo Line)

1. Arraste os PDF para qualquer ponto da janela (ou use **Adicionar PDF…**
   no painel da esquerda). Pode largar **um ou vários** de uma vez, ou ir
   juntando um a um — cada largada soma-se aos que já lá estão, e podem ser
   de formatos diferentes.
2. O formato é **reconhecido sozinho** a partir do conteúdo do PDF:
   - **GDS / ETKT** — PDF do bilhete (`TKT_…`), ou o ecrã GDS do bilhete
     guardado em PDF, um bloco por bilhete;
   - **EasyJet** — PDF de confirmação de pagamento, um bloco por passageiro;
   - **Porto Santo Line** — PDF do bilhete de ferry, um bloco por passageiro
     (nome e NIF) ou viatura (matrícula, sem NIF).
3. Cada documento fica numa linha da lista à esquerda, com o formato, o nº de
   bilhete ou reserva, o passageiro e o total. O texto aparece em
   **Resultado**, um bloco por documento; clicar numa linha da lista salta
   para o bloco respectivo. Um ficheiro já carregado é ignorado se for largado
   outra vez.

### Tarifas

O código da tarifa (*fare basis*) é traduzido para o nome comercial —
`HL0PLU00` → **PLUS**, `Y3BSC` → **BASIC**. Quando o código não é
reconhecido (tarifas de tour operador, por exemplo), assume-se a tarifa base
da companhia: **CLASSIC** na TAP e **BASIC** na SATA.

### Campo XP (opcional)

Escreva um valor extra na pequena caixa **XP** para o somar às taxas. Aplica-se
aos três formatos e é incluído no **Valor Total** de cada bloco. Deixe vazio
para mostrar apenas o total.

### Exportar para o SIGAV

Depois de carregar os PDF, **Enviar para SIGAV** copia as linhas já no
formato da tabela de faturação (Tipo de Custo · Descrição · Qtd · Valor),
prontas a colar. Aplica-se a bilhetes aéreos GDS/ETKT.

> **Nota técnica:** para a extensão de navegador poder preencher a tabela
> sozinha, a aplicação disponibiliza estas linhas numa ponte local, acessível
> **apenas a partir do próprio computador** (`127.0.0.1`). Não abre porta na
> rede nem no firewall, é só de leitura, e o conteúdo expira ao fim de 3
> minutos. Sem a extensão instalada, nada disto é usado — o botão continua a
> copiar para a área de transferência como sempre.
>
> A cópia na área de transferência é só uma reserva (Ctrl+V na página do
> SIGAV) e é **apagada sozinha** assim que a extensão recebe as linhas — ou ao
> fim dos 3 minutos —, para que um Ctrl+V por engano noutro sítio não cole
> nomes, NIF e valores. Se entretanto copiar outra coisa, essa fica.

### Dados — nada fica guardado

**Regra do projecto:** nada sobre os bilhetes fica guardado depois de
processado. Qualquer funcionalidade nova que guarde dados precisa de uma
decisão explícita antes de ser feita.

| Onde podiam ficar | O que a aplicação faz |
|---|---|
| Disco | **Não grava nada** dos bilhetes: nem resultados, nem histórico, nem registo. Só *lê* os PDF. |
| Memória | Os documentos só existem enquanto estão na lista; **×**, **Limpar tudo** ou fechar a aplicação descarta-os. |
| Área de transferência | **Copiar texto** e **Enviar para SIGAV** usam uma cópia privada que o Windows deixa **fora do histórico** (Win+V) e da sincronização na cloud. A do SIGAV sai quando a extensão a recebe (ou aos 3 min). **Ao fechar**, a aplicação limpa o que lá pôs, a não ser que entretanto tenha copiado outra coisa. Se a cópia privada não for possível, aparece um erro — nunca uma cópia normal. |
| Ponte do SIGAV | As linhas ficam em memória no máximo 3 minutos e depois são **apagadas**. Só responde a este computador (`127.0.0.1`) e desaparece quando a aplicação fecha. |

Garantido por `tests/test_no_data_stored.py`. Fora do alcance da aplicação: os
ficheiros abertos com **Adicionar PDF…** ficam nos «Itens recentes» do Windows
(arrastar não deixa rasto), e o que fizer com o texto depois de colado.

### Dicas

- **Copiar texto** — copia o resultado inteiro, para colar noutro sítio.
- **×** — passe o rato por cima de uma linha da lista para retirar só esse
  documento; **Limpar tudo** retira todos.
- **Tema escuro / Tema claro** e **English** — no fundo do painel da esquerda.
- **Acerca** — versão, notas de versão e procurar atualizações.
- O resultado é **apenas apresentado no ecrã** — não é gravado qualquer
  ficheiro no seu disco.
- **Afixar na barra de tarefas:** a aplicação mantém uma identidade fixa, pelo
  que o atalho afixado continua a funcionar depois das atualizações. Se vier de
  uma versão anterior à 1.1.3, remova e volte a afixar **uma única vez**.

### Licença

O **Gerador Faturas** é software **comercial e proprietário** — licenciado,
não vendido. Copyright © 2026 Steven Faria. Todos os direitos reservados.

A utilização exige uma licença válida de Steven Faria. Não é permitida a
redistribuição, a revenda nem a engenharia inversa. Consulte a
[LICENSE](LICENSE) para os termos completos e o
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) para os componentes incluídos.

> **Importante:** esta aplicação é um auxiliar de formatação. Não é software de
> faturação certificada nem um sistema de contabilidade. Todos os valores,
> taxas e totais que produz têm de ser verificados por pessoa qualificada antes
> de serem usados para faturar um cliente ou em qualquer declaração fiscal.

### 🤖 Desenvolvimento assistido por IA

Este software foi **desenvolvido integralmente com assistência de inteligência
artificial generativa**, sob direcção, revisão e controlo editorial de Steven
Faria, que continua a ser o seu autor e responsável para todos os efeitos
legais.

**A aplicação em si não contém qualquer componente de IA.** Não faz
aprendizagem automática, inferência nem decisões automatizadas: o processamento
é totalmente determinístico — a mesma entrada produz sempre a mesma saída.
Nenhum dado, documento ou dado pessoal do utilizador é enviado para sistemas de
IA, para o autor ou para terceiros; todo o processamento decorre localmente na
máquina do utilizador.

> **Nota legal:** por não ser um «sistema de IA» na acepção do artigo 3.º, n.º 1
> do Regulamento (UE) 2024/1689 (Regulamento da Inteligência Artificial), não
> lhe são aplicáveis as obrigações de transparência do artigo 50.º do mesmo
> Regulamento. Esta divulgação é feita **voluntariamente**, por transparência.
> O dever de verificação por pessoa qualificada mantém-se integralmente (ver
> cláusula 5 da [LICENSE](LICENSE)).

</details>

---

<details>
<summary><h2>🇬🇧 &nbsp;English</h2></summary>

### Installing

1. Go to the [latest release](https://github.com/McGliebs/projectinvoice/releases/latest).
2. Download **`GeradorFaturas.exe`**.
3. Run it — no installation required.

On first run Windows may show a SmartScreen warning (the app is not code-signed):
click **More info → Run anyway**.

> The app checks for updates automatically on startup. When a newer version is
> available it offers to download and install it, then restarts itself.

### Using it — PDFs (GDS / ETKT, EasyJet, Porto Santo Line)

1. Drag the PDFs anywhere onto the window (or use **Add PDF…** in the left
   panel). You can drop **one or several** at once, or add them one at a
   time — each drop adds to what is already loaded, and formats can be mixed.
2. The format is **detected automatically** from the PDF's content:
   - **GDS / ETKT** — ticket PDF (`TKT_…`), or the GDS ticket display saved
     as a PDF, one block per ticket;
   - **EasyJet** — payment-confirmation PDF, one block per passenger;
   - **Porto Santo Line** — ferry ticket PDF, one block per passenger (name
     and NIF) or vehicle (licence plate, no NIF).
3. Each document gets a row in the list on the left, with its format, ticket
   or booking number, passenger and total. The text appears under
   **Result**, one block per document; clicking a row jumps to its block. A
   file that is already loaded is skipped if dropped again.

### Fare types

The fare basis code is translated to its commercial name — `HL0PLU00` →
**PLUS**, `Y3BSC` → **BASIC**. When the code isn't recognised (tour-operator
fares, for instance), the airline's base fare is assumed: **CLASSIC** for TAP
and **BASIC** for SATA.

### XP field (optional)

Type an extra amount in the small **XP** box to add it to the taxes. It applies
to all three formats and is included in each block's **Valor Total**. Leave it
empty to show the total only.

### Exporting to SIGAV

Once the PDFs are loaded, **Send to SIGAV** copies the rows already in
the billing-table format (Tipo de Custo · Descrição · Qtd · Valor), ready to
paste. Applies to GDS/ETKT air tickets.

> **Technical note:** so the browser extension can fill the table on its own,
> the app also serves these rows over a local bridge reachable **only from this
> computer** (`127.0.0.1`). It opens no network or firewall port, is read-only,
> and the content expires after 3 minutes. Without the extension installed none
> of this is used — the button still copies to the clipboard as before.
>
> The clipboard copy is only a fallback (Ctrl+V on the SIGAV page) and is
> **cleared automatically** as soon as the extension receives the rows — or
> after the 3 minutes — so a mistaken Ctrl+V elsewhere doesn't paste names, tax
> numbers and amounts. If you copy something else in the meantime, that stays.

### Data — nothing is stored

**Project rule:** nothing about the tickets is kept after processing. Any new
feature that would keep data needs an explicit decision first.

| Where data could stay | What the app does |
|---|---|
| Disk | **Writes nothing** from the tickets: no results, no history, no log. It only *reads* the PDFs. |
| Memory | Documents exist only while they're in the list; **×**, **Clear all** or closing the app discards them. |
| Clipboard | **Copy text** and **Send to SIGAV** use a private copy that Windows keeps **out of clipboard history** (Win+V) and cloud sync. The SIGAV copy is removed when the extension receives it (or after 3 min). **On exit** the app clears what it put there, unless you've copied something else since. If a private copy isn't possible you get an error — never an ordinary copy. |
| SIGAV bridge | Rows are held in memory for at most 3 minutes, then **wiped**. It only answers this computer (`127.0.0.1`) and disappears when the app closes. |

Enforced by `tests/test_no_data_stored.py`. Outside the app's control: files
opened with **Add PDF…** go into Windows "Recent items" (drag and drop leaves no
trace), and what you do with the text after pasting it.

### Tips

- **Copy text** — copies the whole result, to paste elsewhere.
- **×** — hover over a row in the list to remove just that document; **Clear
  all** removes them all.
- **Dark theme / Light theme** and **Português** — at the bottom of the left
  panel.
- **About** — version, release notes and checking for updates.
- The result is **shown on screen only** — no file is written to your disk.
- **Pinning to the taskbar:** the app keeps a fixed identity, so a pinned
  shortcut keeps working across updates. Coming from a version older than
  1.1.3, unpin and re-pin **once**.

### Licence

**Gerador Faturas is commercial, proprietary software — licensed, not sold.**
Copyright © 2026 Steven Faria. All rights reserved.

Use requires a valid licence from Steven Faria. Redistribution, resale, and
reverse engineering are not permitted. See [LICENSE](LICENSE) for the full terms
and [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for the bundled components.

> **Important:** this application is a formatting aid. It is not certified
> invoicing software and not an accounting system. All amounts, taxes, and
> totals it produces must be verified by a qualified person before being used to
> invoice a client or in any fiscal declaration.

### 🤖 AI-assisted development

This software was **developed entirely with the assistance of generative
artificial intelligence**, under the direction, review, and editorial control of
Steven Faria, who remains its author and provider for all legal purposes.

**The application itself contains no AI component.** It performs no machine
learning, no inference, and no automated decision-making: all processing is
deterministic — identical input always produces identical output. No user data,
document, or personal data is sent to any AI system, to the author, or to any
third party; all processing happens locally on the user's machine.

> **Legal note:** because it is not an "AI system" within the meaning of
> Article 3(1) of Regulation (EU) 2024/1689 (the Artificial Intelligence Act),
> the transparency obligations of Article 50 of that Regulation do not apply to
> it. This disclosure is made **voluntarily**, in the interest of transparency.
> The duty of verification by a qualified person applies in full (see clause 5
> of the [LICENSE](LICENSE)).

</details>

---

<sub>Windows · atualizações automáticas via GitHub Releases · Developed by Steven Faria · Desenvolvido com assistência de IA / Developed with AI assistance · © 2026 Steven Faria. Todos os direitos reservados.</sub>
