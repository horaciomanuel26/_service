<div align="center">
  <img src="asset/logo.png" alt="Logo do _service — API de Teste" width="700">

  # _service — API de Teste

  **Uma coleção pública de dados JSON para testes e desenvolvimento.**
</div>

---

## Sobre o projeto

O **_service** disponibiliza conjuntos de dados fictícios em formato JSON para programadores testarem aplicações web, aplicações mobile e integrações que consomem dados através de HTTP.

Os ficheiros são hospedados no GitHub Pages e disponibilizados para consulta pública. Esta é uma API estática e **somente de leitura**: os endpoints permitem requisições `GET`.

## Base URL

Quando o GitHub Pages estiver ativado e publicado, a base URL será:

```text
https://horaciomanuel26.github.io/_service/api
```

## Endpoints disponíveis

| Endpoint | Descrição | Registos |
|---|---|---:|
| `/noticias.json` | Notícias de tecnologia | 50 |
| `/produtos.json` | Produtos, preços e categorias | 50 |
| `/usuarios.json` | Utilizadores e perfis | 50 |
| `/musicas.json` | Artistas, álbuns e músicas | 50 |
| `/filmes.json` | Filmes, géneros e avaliações | 50 |
| `/receitas.json` | Receitas e ingredientes | 50 |
| `/cursos.json` | Cursos, módulos e duração | 50 |
| `/viagens.json` | Destinos e pontos turísticos | 50 |
| `/empresas.json` | Empresas e funcionários | 50 |
| `/jogos.json` | Jogos, plataformas e classificações | 50 |

Cada ficheiro contém 50 registos, totalizando **500 registos**.

## Como consumir a API

Podes utilizar os endpoints em JavaScript, React, React Native, PHP, Python ou noutra tecnologia que suporte requisições HTTP.

### Exemplo com JavaScript (Fetch)

```javascript
const API_URL = "https://horaciomanuel26.github.io/_service/api";

async function buscarNoticias() {
  try {
    const resposta = await fetch(`${API_URL}/noticias.json`);

    if (!resposta.ok) {
      throw new Error("Não foi possível obter os dados.");
    }

    const noticias = await resposta.json();
    console.log(noticias);
  } catch (erro) {
    console.error("Erro ao consultar a API:", erro);
  }
}

buscarNoticias();
```

### Exemplo com React Native

```javascript
const API_URL = "https://horaciomanuel26.github.io/_service/api";

async function buscarProdutos() {
  try {
    const resposta = await fetch(`${API_URL}/produtos.json`);

    if (!resposta.ok) {
      throw new Error("Não foi possível obter os produtos.");
    }

    const produtos = await resposta.json();
    console.log(produtos);
  } catch (erro) {
    console.error("Erro ao consultar produtos:", erro);
  }
}
```

## Método HTTP permitido

O acesso aos dados é feito através do método:

| Método | Finalidade |
|---|---|
| `GET` | Consultar os ficheiros JSON |

Não são disponibilizadas operações de escrita através de `POST`, `PUT`, `PATCH` ou `DELETE`. Para alterar os dados, é necessário editar os ficheiros diretamente no repositório e publicar as alterações.

## Estrutura do projeto

```text
_service/
│
├── api/
│   ├── noticias.json
│   ├── produtos.json
│   ├── usuarios.json
│   ├── musicas.json
│   ├── filmes.json
│   ├── receitas.json
│   ├── cursos.json
│   ├── viagens.json
│   ├── empresas.json
│   └── jogos.json
│
├── asset/
│   └── logo.png
│
└── README.md
```

## Características e limitações

- 10 conjuntos de dados em formato JSON.
- 50 registos por ficheiro — 500 no total.
- Acesso público, sem autenticação.
- Consulta somente através de `GET`.
- Não possui base de dados nem backend dinâmico.
- Os dados não são alterados automaticamente.
- A disponibilidade dos endpoints depende da publicação do GitHub Pages.

## Objetivo

O projeto foi criado para fins educativos e de desenvolvimento, permitindo praticar o consumo de APIs, a apresentação de dados, a pesquisa, a filtragem e outras funcionalidades em aplicações web e mobile.

## Aviso

Todos os dados disponibilizados são fictícios e destinam-se exclusivamente a testes, demonstrações e aprendizagem. Não devem ser considerados informações reais.
