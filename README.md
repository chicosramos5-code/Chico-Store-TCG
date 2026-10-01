# Chico Store TCG — ERP

Sistema de gestão da **Chico Store TCG**: vendas (Jamble, WhatsApp…), pedidos de compra, estoque, insumos, contas a pagar e a receber, consignado e dashboard.

- Site: GitHub Pages (conta GitHub da loja)
- Dados: Google Sheets + Apps Script **na conta Google da loja** — nenhum dado passa por outra conta.
- Acesso: somente o e-mail da loja.

---

## Instalação (uma vez só)

### 1) Planilha e Apps Script — logado na conta Google da loja
1. Entre no Google com o **e-mail da loja**.
2. Crie uma planilha nova no Google Sheets (nome sugerido: *Chico Store TCG — ERP*).
3. Menu **Extensões › Apps Script**. Apague o que estiver lá e cole o conteúdo de `Code.gs` (enviado à parte).
4. Selecione a função **setup** e clique em **Executar**. Autorize o acesso (planilha, Drive e e-mail).
5. **Implantar › Nova implantação › Tipo: App da Web**
   - Executar como: **Eu**
   - Quem pode acessar: **Qualquer pessoa**
6. Copie a **URL do App da Web** (termina em `/exec`).

> O `Code.gs` libera o acesso **somente para a conta Google dona do script** (a da loja). Fotos, backups e o e-mail de "esqueci a senha" ficam/vão só para essa conta.

### 2) GitHub — conta GitHub da loja
1. Crie um repositório novo (ex.: `chicostore-erp`) na conta GitHub da loja.
2. Envie todos os arquivos deste zip para a branch **main**.
3. Edite o arquivo **`config.js`** no GitHub:
   - `apiUrl:` cole a URL `/exec` do passo 1
   - `email:` o e-mail da loja
4. **Settings › Pages › Source: Deploy from a branch › main / (root) › Save**.
5. Em 1–2 minutos o site fica em `https://SEU-USUARIO.github.io/chicostore-erp/`.

### 3) Primeiro acesso
1. Abra o site › **Criar novo acesso** › crie a senha.
2. No Painel, clique em **Informar saldos** (ou Configurações › Saldos de abertura) e preencha:
   - saldo da conta do banco
   - valores da Jamble (disponível e pendente), se houver
3. Cadastre fornecedores e produtos (ou importe as etiquetas da Jamble).

### Pedidos já pagos que ainda não chegaram — "Importação"
Em **Pedidos de compra › Novo pedido**, use a forma de pagamento **Importação**:
- não gera contas a pagar e não mexe no saldo em conta (já foi pago);
- deixe a situação **Em aberto** — o valor aparece no card **Estoque a receber**;
- quando chegar, clique em **Receber** (ou **Chegou** no card do Painel): entra no estoque e atualiza o custo.
- Se ainda faltam parcelas a pagar desse pedido, lance em Contas a pagar › Nova conta › "Conta já parcelada".

---

## Atualizações
- Arquivos do site: substitua no GitHub (branch main).
- `Code.gs`: cole por cima no Apps Script, rode **setup** e depois **Implantar › Gerenciar implantações › lápis › Nova versão › Implantar** (a URL continua a mesma).

## Versões
### v1.0 (01/10/2026)
- Base: ERP completo (vendas, compras, estoque, insumos, financeiro, consignado, Jamble, dashboard).
- Identidade visual Chico Store TCG (roxo, dourado e azul da logo).
- Animação de entrada: círculo mágico + roleta de processamento.
- Sócio: Francisco Sampaio Ramos (retiradas a custo).
- Forma de pagamento **Importação** sempre disponível.
- Pix / Boleto à vista: a conta já nasce paga na data do pedido.
