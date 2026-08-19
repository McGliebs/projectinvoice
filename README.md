# Gerador de Faturas

Converts airline billing data into clean, formatted text invoices.
Converte dados de faturação aérea em faturas de texto limpas e formatadas.

Supported inputs / Formatos suportados:
- **GDS Amadeus** (TAP / SATA) — direct flights and connections / voos directos e ligações
- **easyJet** — payment confirmation PDF / PDF de confirmação de pagamento

---

## English

### Installing
1. Go to the [latest release](https://github.com/McGliebs/projectinvoice/releases/latest).
2. Download **`GeradorFaturas.exe`**.
3. Run it — no installation needed. Windows may show a SmartScreen warning the
   first time (unsigned app): click **More info → Run anyway**.

The app checks for updates automatically on startup. When a newer version
exists, it offers to download and install it, then relaunches itself.

### Using it — GDS (TAP / SATA)
1. Paste the raw GDS text into the **INPUT** box.
2. Click **⚡ Gerar TXT**.
3. The formatted invoice appears in **OUTPUT**, ready to select and copy.

**Multiple tickets at once:** paste several tickets in sequence (each starting
with a `TKT-…` line, followed by its `TWD/TAX` tax detail). Each passenger is
formatted as its own block.

**XP field (optional):** type an extra amount in the small **XP** box to add it
to the taxes and the **Valor Total**. Leave it empty to just show the total.

### Using it — easyJet
1. **Drag the easyJet payment-confirmation PDF** onto the drop zone (or click it
   to browse).
2. The invoice is generated and saved automatically.

### Tips
- **☀ / 🌙** toggles light / dark theme.
- **Clear** clears the input, output and drop zones.
- The result is shown on screen only — no file is written to your disk.

---

## Português (PT-PT)

### Instalação
1. Vá à [versão mais recente](https://github.com/McGliebs/projectinvoice/releases/latest).
2. Descarregue o **`GeradorFaturas.exe`**.
3. Execute — não precisa de instalação. Na primeira vez, o Windows pode mostrar
   um aviso do SmartScreen (app sem assinatura): clique em
   **Mais informações → Executar mesmo assim**.

A aplicação procura atualizações automaticamente ao arrancar. Quando existe uma
versão mais recente, propõe descarregar e instalar, e depois reinicia-se.

### Utilização — GDS (TAP / SATA)
1. Cole o texto GDS em bruto na caixa **INPUT**.
2. Clique em **⚡ Gerar TXT**.
3. A fatura formatada aparece em **OUTPUT**, pronta a seleccionar e copiar.

**Vários bilhetes de uma vez:** cole vários bilhetes em sequência (cada um a
começar por uma linha `TKT-…`, seguida do respectivo detalhe de taxas
`TWD/TAX`). Cada passageiro é formatado no seu próprio bloco.

**Campo XP (opcional):** escreva um valor extra na pequena caixa **XP** para o
somar às taxas e ao **Valor Total**. Deixe vazio para apenas mostrar o total.

### Utilização — easyJet
1. **Arraste o PDF de confirmação de pagamento** da easyJet para a zona de
   largar (ou clique para procurar o ficheiro).
2. A fatura é gerada e guardada automaticamente.

### Dicas
- **☀ / 🌙** alterna entre tema claro e escuro.
- **Limpar** limpa o input, o output e as zonas de largar.
- O resultado é apenas apresentado no ecrã — não é gravado qualquer ficheiro.

---

## Licence / Licença

**Gerador de Faturas is commercial, proprietary software — licensed, not sold.**
Copyright © 2026 Steven Faria. All rights reserved. *Developed by Steven Faria.*

Use requires a valid licence from Steven Faria. Redistribution, resale, and
reverse engineering are not permitted. See [LICENSE](LICENSE) for the full terms
and [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for the bundled components.

> **Important:** this application is a formatting aid, not certified invoicing
> or accounting software. All amounts, taxes, and totals it produces must be
> verified by a qualified person before being used to invoice a client or in any
> fiscal declaration.

---

O **Gerador de Faturas** é software **comercial e proprietário** — licenciado,
não vendido. Copyright © 2026 Steven Faria. Todos os direitos reservados.

A utilização exige uma licença válida de Steven Faria. Não é permitida a
redistribuição, revenda ou engenharia inversa. Consulte a [LICENSE](LICENSE)
para os termos completos e o [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)
para os componentes incluídos.

> **Importante:** esta aplicação é um auxiliar de formatação, não é software de
> faturação certificada nem um sistema de contabilidade. Todos os valores, taxas
> e totais que produz têm de ser verificados por pessoa qualificada antes de
> serem usados para faturar um cliente ou em qualquer declaração fiscal.

---

<sub>Windows · atualizações automáticas via GitHub Releases · © 2026 Steven Faria.</sub>
