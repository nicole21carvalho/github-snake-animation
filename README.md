# 🐍 Animação da cobrinha do GitHub

Workflow do **GitHub Actions** que transforma o gráfico de contribuições do meu perfil numa animação da cobrinha "comendo" os quadradinhos, atualizada automaticamente a cada 12 horas.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/nicole21carvalho/github-snake-animation/output/snake-dark.svg">
    <img alt="Cobrinha comendo o gráfico de contribuições" src="https://raw.githubusercontent.com/nicole21carvalho/github-snake-animation/output/snake.svg">
  </picture>
</p>

## ⚙️ Como funciona

O workflow [`.github/workflows/snake.yml`](.github/workflows/snake.yml):

1. Usa a action [Platane/snk](https://github.com/Platane/snk) para ler o gráfico de contribuições
2. Gera duas versões: `snake.svg` (tema claro) e `snake-dark.svg` (tema escuro)
3. Publica os arquivos na branch `output` com a action [crazy-max/ghaction-github-pages](https://github.com/crazy-max/ghaction-github-pages)

Ele roda a cada 12 horas, a cada push na `main` e quando é disparado manualmente pela aba **Actions**.

## 🧠 Detalhes da configuração

- **Agendamento:** `0 */12 * * *` roda no minuto 0, duas vezes por dia. (Um erro comum é usar `* */12 * * *`, que roda a cada minuto durante a hora 0 e a hora 12, ou seja, 120 vezes por dia.)
- **Permissão mínima:** o job só recebe `contents: write`, o necessário para publicar na branch `output`.
- **`concurrency`:** se duas execuções começarem juntas, a mais antiga é cancelada, para não haver conflito ao publicar.
- **Tema claro e escuro:** o README usa `<picture>` para mostrar a versão certa conforme o tema de quem está vendo.

## 🚀 Como usar no seu perfil

1. Copie o [`snake.yml`](.github/workflows/snake.yml) para `.github/workflows/` no repositório do seu perfil (aquele com o mesmo nome do seu usuário)
2. Rode o workflow uma vez pela aba **Actions**
3. Coloque no README do perfil, trocando `SEU_USUARIO`:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SEU_USUARIO/SEU_USUARIO/output/snake-dark.svg">
  <img alt="Cobrinha comendo o gráfico de contribuições" src="https://raw.githubusercontent.com/SEU_USUARIO/SEU_USUARIO/output/snake.svg">
</picture>
```
