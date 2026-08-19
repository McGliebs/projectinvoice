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
3. The formatted invoice appears in **OUTPUT** and is saved to
   `output\resultado.txt`.

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
- **Limpar** clears the input, output and drop zone (it does **not** delete the
  saved `output\resultado.txt`).
- The result is always written to `output\resultado.txt` next to the app.

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
3. A fatura formatada aparece em **OUTPUT** e é guardada em
   `output\resultado.txt`.

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
- **Limpar** limpa o input, o output e a zona de largar (**não** apaga o
  ficheiro guardado `output\resultado.txt`).
- O resultado é sempre gravado em `output\resultado.txt`, junto à aplicação.

---

<sub>Windows · atualizações automáticas via GitHub Releases.</sub>
