# _service — API de Teste

Uma API pública e gratuita que disponibiliza conjuntos de dados fictícios em formato JSON para testes e desenvolvimento de aplicações.

## Sobre o projecto

O `_service` foi criado para facilitar os testes de aplicações web e mobile, permitindo aos programadores consumir dados externos sem precisar de desenvolver um backend ou configurar uma base de dados.

Os dados são disponibilizados através de ficheiros JSON hospedados no GitHub Pages.

**Esta API é somente de leitura: permite exclusivamente requisições GET.**

## Base URL

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

## Método HTTP

O único método disponibilizado para consulta é:

- `GET` — obter os dados.

Não são suportadas operações `POST`, `PUT`, `PATCH` ou `DELETE`.

## Como utilizar

### JavaScript — Fetch

```javascript
const API_URL = "https://horaciomanuel26.github.io/_service/api";

async function buscarNoticias() {
    try {
        const resposta = await fetch(`${API_URL}/noticias.json`);

        if (!resposta.ok) {
            throw new Error("Erro ao consultar a API.");
        }

        const noticias = await resposta.json();

        console.log(noticias);
    } catch (erro) {
        console.error(erro);
    }
}

buscarNoticias();
```

### React Native — Fetch

```javascript
const API_URL = "https://horaciomanuel26.github.io/_service/api";

async function buscarProdutos() {
    try {
        const resposta = await fetch(`${API_URL}/produtos.json`);

        const produtos = await resposta.json();

        console.log(produtos);
    } catch (erro) {
        console.error("Erro:", erro);
    }
}
```

## Estrutura do projecto

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
└── README.md
```

## Características

- 10 conjuntos de dados.
- 50 registos por ficheiro.
- 500 registos no total.
- Dados em formato JSON.
- Acesso público.
- Sem autenticação.
- Somente leitura (GET).
- Compatível com aplicações web e mobile.

## Limitações

Por ser uma API baseada em ficheiros estáticos:

- Não possui base de dados.
- Não permite criar, editar ou eliminar registos através de requisições HTTP.
- Os dados só são actualizados quando os ficheiros são modificados no repositório.
- A disponibilidade depende da hospedagem do GitHub Pages.

## Finalidade

Este projecto destina-se a fins educativos, testes e desenvolvimento de aplicações que necessitam de consumir dados através de requisições HTTP.

**Nota:** Todos os dados disponibilizados são fictícios e devem ser utilizados exclusivamente para testes e demonstrações.