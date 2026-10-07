# 🐍 Animação da cobrinha do GitHub

Workflow do **GitHub Actions** que gera a animação da cobrinha "comendo" o gráfico de contribuições do meu perfil.

## ⚙️ Como funciona

O arquivo [`snake.yml`](snake.yml) usa a action [Platane/snk](https://github.com/Platane/snk) para:

1. Ler o gráfico de contribuições do perfil
2. Gerar o `snake.svg` no tema escuro do GitHub
3. Publicar a imagem na branch `output`

Ele roda de 12 em 12 horas, em todo push na `master` e quando é disparado manualmente.

## 🚀 Como usar no seu perfil

1. Copie o `snake.yml` para `.github/workflows/` no repositório do seu perfil
2. Rode o workflow uma vez pela aba **Actions**
3. Coloque a imagem no README do perfil:

```markdown
![Cobrinha](https://raw.githubusercontent.com/SEU_USUARIO/SEU_USUARIO/output/snake.svg)
```
