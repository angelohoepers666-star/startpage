# Startpage

Startpage minimalista para Firefox com relógio, clima, frase do dia e links organizados por categoria.

## Customização

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

Após editar, limpe o localStorage para o arquivo assumir os novos defaults, ou limpe o cache da nova página/aba:

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
