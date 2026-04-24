<<<<<<< HEAD
# Startpage

Startpage minimalista para Firefox com relógio, clima, frase do dia e links organizados por categoria.

## Uso no Firefox

1. Abra o Firefox
2. Na barra de endereço: `about:preferences#home`
3. Em **Homepage and new windows** → **Custom URLs** → cole o caminho absoluto:
   - Linux/Mac: `file:///home/SEU_USUARIO/startpage/index.html`
   - Windows: `file:///C:/Users/SEU_USUARIO/startpage/index.html`

## Setup com Git

```bash
# Criar repositório (primeiro uso)
git init
git add index.html README.md
git commit -m "feat: startpage inicial"

# Adicionar remote (GitHub/GitLab privado recomendado)
git remote add origin git@github.com:SEU_USER/startpage.git
git push -u origin main
```

### Sincronizar entre casa e trabalho

```bash
# Ao chegar (puxar mudanças)
git pull

# Ao sair (salvar mudanças)
git add index.html
git commit -m "chore: atualiza links"
git push
```

## Customização

### Editar links pela interface
Clique no botão **editar** (canto inferior direito) para:
- Adicionar novos links em qualquer categoria
- Editar nome, URL, ícone e cor de links existentes
- Remover links (botão × vermelho)

> **Atenção:** as edições feitas pela UI ficam no `localStorage` do Firefox. Para sincronizar via git, use o método abaixo.

### Editar links no arquivo (recomendado para git)

Abra `index.html` e localize `DEFAULT_CATEGORIES`. Edite o array diretamente:

```js
{
  id: 'trabalho',
  label: 'Trabalho',
  links: [
    { name: 'GitHub', url: 'https://github.com', icon: '🐙', color: '#e8e8ea' },
    // adicione mais aqui...
  ]
}
```

Após editar, limpe o localStorage para o arquivo assumir os novos defaults:
1. `F12` → Console → `localStorage.removeItem('startpage_v2')` → `Enter`
2. Recarregue a página (`F5`)

### Alterar cidade do clima

Encontre no arquivo:
```js
const WEATHER_LAT = -26.3056;
const WEATHER_LON = -48.8456;
const WEATHER_CITY = 'Joinville, SC';
```

Substitua pelas coordenadas da sua cidade. Use [latlong.net](https://www.latlong.net/) para encontrar.

### Adicionar frases do dia

Encontre `const SPLASHES = [...]` e adicione suas frases ao array.

## Estrutura

```
startpage/
└── index.html   # tudo em um único arquivo, zero dependências externas
```

O clima usa a API [Open-Meteo](https://open-meteo.com/) — gratuita, sem API key.
=======
# startpage
Página inicial para novas abas.
>>>>>>> 1b694023fc0cc9a99c9c3169c8edd7970c619661
