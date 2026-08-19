# Gerador Faturas para SSM

Converte dados de faturação aérea e marítima em faturas de texto formatadas.
*Converts airline and ferry billing data into clean, formatted text invoices.*

**Formatos suportados / Supported formats**

| Formato | Origem / Source |
|---|---|
| **GDS Amadeus** | TAP / SATA — texto colado (voos directos e ligações) |
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

### Utilização — GDS (TAP / SATA)

1. Cole o texto GDS em bruto na caixa **INPUT**.
2. Clique em **⚡ Gerar TXT**.
3. A fatura formatada aparece em **OUTPUT**, pronta a seleccionar e copiar.

**Vários bilhetes de uma vez** — cole vários bilhetes em sequência, cada um a
começar por uma linha `TKT-…` seguida do respectivo detalhe de taxas
(`TWD/TAX`). Cada passageiro é formatado no seu próprio bloco.

### Utilização — EasyJet

1. Arraste o **PDF de confirmação de pagamento** para a zona de largar da
   EasyJet (ou clique nela para procurar o ficheiro).
2. A fatura aparece em **OUTPUT** — um bloco por passageiro.

### Utilização — Porto Santo Line (ferry)

1. Arraste o **PDF do bilhete de ferry** para a zona de largar da Porto Santo
   Line (ou clique nela para procurar o ficheiro).
2. A fatura aparece em **OUTPUT**, com um bloco por passageiro ou viatura:
   - **Passageiros** — nome e NIF;
   - **Viaturas** — matrícula, sem NIF.

### Campo XP (opcional)

Escreva um valor extra na pequena caixa **XP** para o somar às taxas. Aplica-se
aos três formatos e é incluído no **Valor Total** de cada bloco. Deixe vazio
para mostrar apenas o total.

### Dicas

- **☀ / 🌙** — alterna entre tema claro e escuro.
- **🌐 PT / EN** — alterna o idioma da interface.
- **Limpar** — limpa o input, o output e as zonas de largar.
- O resultado é **apenas apresentado no ecrã** — não é gravado qualquer
  ficheiro no seu disco.

### Licença

O **Gerador Faturas para SSM** é software **comercial e proprietário** — licenciado,
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

### Using it — GDS (TAP / SATA)

1. Paste the raw GDS text into the **INPUT** box.
2. Click **⚡ Generate TXT**.
3. The formatted invoice appears in **OUTPUT**, ready to select and copy.

**Several tickets at once** — paste multiple tickets in sequence, each starting
with a `TKT-…` line followed by its tax detail (`TWD/TAX`). Each passenger is
formatted as its own block.

### Using it — EasyJet

1. Drag the **payment-confirmation PDF** onto the EasyJet drop zone (or click
   the zone to browse for the file).
2. The invoice appears in **OUTPUT** — one block per passenger.

### Using it — Porto Santo Line (ferry)

1. Drag the **ferry ticket PDF** onto the Porto Santo Line drop zone (or click
   the zone to browse for the file).
2. The invoice appears in **OUTPUT**, one block per passenger or vehicle:
   - **Passengers** — name and NIF (tax number);
   - **Vehicles** — licence plate, no NIF.

### XP field (optional)

Type an extra amount in the small **XP** box to add it to the taxes. It applies
to all three formats and is included in each block's **Valor Total**. Leave it
empty to show the total only.

### Tips

- **☀ / 🌙** — toggles light / dark theme.
- **🌐 PT / EN** — switches the interface language.
- **Clear** — clears the input, output and drop zones.
- The result is **shown on screen only** — no file is written to your disk.

### Licence

**Gerador Faturas para SSM is commercial, proprietary software — licensed, not sold.**
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
