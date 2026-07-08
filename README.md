# Tabela da Copa — versão web interativa

Recriação interativa do pôster radial do mata-mata da Copa do Mundo (32 seleções,
troféu no centro). Clique em uma seleção para avançá-la à próxima fase; clique de
novo para desfazer. Os resultados são salvos automaticamente no navegador
(`localStorage`) — ao voltar à página, sua tabela continua preenchida.

- **`index.html`** — página única, sem dependências (SVG + JavaScript puro).
- **`trophy.png`** — troféu extraído da arte original.
- **`crests/`** — brasões das 32 federações extraídos da arte original; aparecem
  no anel externo (apenas decorativos, não clicáveis — o clique é nos círculos
  de bandeira).
- **Palpite original** — botão que preenche a tabela com os resultados do pôster
  (até as quartas de final, onde a arte parava).
- **Limpar** — zera todos os resultados.

## Como funciona o chaveamento

8 grupos de 4 seleções dispostos em círculo → 16 jogos na rodada de 32 →
oitavas → quartas (pontos nas diagonais do anel dourado) → semifinais →
final no troféu. Ao definir o campeão, o nome aparece sob o troféu e o anel
acende na cor da seleção. Trocar um resultado antigo limpa automaticamente
os jogos seguintes que dependiam dele.

## Publicando no GitHub Pages

O deploy já está automatizado em `.github/workflows/deploy.yml`. Basta:

1. Criar um repositório no GitHub e enviar o projeto:

   ```bash
   git init
   git add .
   git commit -m "Tabela da Copa interativa"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/tabela-copa.git
   git push -u origin main
   ```

2. No repositório, abrir **Settings → Pages** e em **Build and deployment →
   Source** escolher **GitHub Actions**.

3. Pronto — cada push na branch `main` publica o site em
   `https://SEU_USUARIO.github.io/tabela-copa/`.

## Rodando localmente

É um site estático: basta abrir o `index.html` no navegador
(ou servir a pasta com `npx serve`, por exemplo).
