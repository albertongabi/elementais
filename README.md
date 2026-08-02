# Meus Elementais — atualização automática

## Arquivos para subir
Suba **todo o conteúdo desta pasta** para a raiz do repositório, preservando as pastas `.github/workflows` e `scripts`.

## Configuração no GitHub
1. Em **Settings → Actions → General → Workflow permissions**, marque **Read and write permissions**.
2. Em **Settings → Pages → Build and deployment**, selecione **Source: GitHub Actions**.
3. Abra **Actions → Atualizar e publicar elementais → Run workflow** para o primeiro teste.

## Como funciona
- `index.html` lê `elementais.json` ao abrir e mantém o progresso no `localStorage` do aparelho.
- A Action consulta cada guia em `fortniteking.com/sprite/<slug>` diariamente.
- O script considera `Drop Em breve` como `em_breve`; qualquer percentual, inclusive `0%`, como disponível.
- Se a estrutura do FortniteKing mudar e poucas combinações forem reconhecidas, a Action falha sem substituir o catálogo por dados vazios.

## Horário
O cron `17 12 * * *` roda aproximadamente às 09:17 no horário de Brasília (UTC−3). O GitHub pode atrasar workflows agendados em horários de pico.

## Observação importante
John Wick, Amendoim Torrado, Pollo, Vini Jr. e Ironmouse estão configurados com somente a variação Normal. O robô respeita `variantesDisponiveis` e não adiciona outras variações automaticamente a esses tipos.
