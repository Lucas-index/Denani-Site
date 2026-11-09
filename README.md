# 🎵 Sistema Musical

Protótipo **front-end** (Sprint 1) de um sistema para cadastrar artistas e músicas e consultar uma biblioteca musical. O projeto usa apenas **HTML5 e CSS3**, sem JavaScript e sem back-end. Os dados exibidos são fictícios e servem para validar o layout e a navegação.

> 🚧 **Status:** Sprint 1 concluída (telas estáticas). A **Sprint 2** vai adicionar o back-end em PHP e o banco de dados.

---

## 📋 Índice

- [Telas](#-telas)
- [Fluxo de navegação](#-fluxo-de-navegação)
- [Estrutura de arquivos](#-estrutura-de-arquivos)
- [Como executar](#-como-executar)
- [Credenciais de teste](#-credenciais-de-teste)
- [Campos dos formulários](#-campos-dos-formulários)
- [Planejamento da Sprint 2](#-planejamento-da-sprint-2)
- [Tecnologias](#-tecnologias)

---

## 🖥️ Telas

| Arquivo | Tela | Descrição |
|---|---|---|
| `login.html` | Login | Formulário de usuário e senha, com dica das credenciais de teste. |
| `index.html` | Menu Principal | Boas-vindas e 3 cards de acesso: artistas, músicas e biblioteca. Tem o botão **Sair**. |
| `cadastro_artista.html` | Gerenciar Artistas | Formulário de novo artista e tabela de artistas cadastrados, com ações de editar, excluir e ir para as músicas. |
| `cadastro_musica.html` | Nova Música | Formulário para cadastrar uma música vinculada a um artista. |
| `listagem_musicas.html` | Biblioteca Musical | Filtros (busca geral, artista e gênero) e tabela com todas as músicas e link para o YouTube. |

---

## 🧭 Fluxo de navegação

```
login.html
   │  (Entrar)
   ▼
index.html  ◄──────────────────────────────┐
   │                                       │
   ├── Gerenciar Artistas ─► cadastro_artista.html
   │                              │
   │                              └── botão "🎵 Músicas" ─► cadastro_musica.html
   │                                                             │
   │                                      "Voltar para Artistas" ┘
   │
   ├── Cadastrar Músicas ─► cadastro_musica.html
   │
   └── Biblioteca Musical ─► listagem_musicas.html
                                  └── "➕ Nova Música" ─► cadastro_musica.html
```

O botão **Sair** do menu leva de volta ao `login.html`.

---

## 📁 Estrutura de arquivos

```
.
├── _gitattributes          # Configuração de atributos do Git (renomear para .gitattributes)
├── styles.css              # Estilo único, usado por todas as telas
├── login.html              # Tela de login
├── index.html              # Menu principal
├── cadastro_artista.html   # Cadastro e listagem de artistas
├── cadastro_musica.html    # Cadastro de músicas
└── listagem_musicas.html   # Biblioteca musical com filtros
```

Todas as telas compartilham o mesmo `styles.css`, o que mantém o visual consistente e facilita a manutenção. Os arquivos HTML têm comentários didáticos explicando cada trecho.

---

## ▶️ Como executar

Não é preciso instalar nada.

1. Clone ou baixe o repositório.
2. Abra o arquivo `login.html` no navegador (duplo clique ou *Abrir com…*).
3. Navegue pelas telas usando os botões e links.

Se preferir um servidor local, por exemplo com a extensão **Live Server** do VS Code, abra a pasta e inicie o servidor a partir do `login.html`.

> ℹ️ Os formulários usam `action="#"`, então **nenhum dado é enviado ou salvo** por enquanto.

---

## 🔑 Credenciais de teste

| Usuário | Senha |
|---|---|
| `admin` | `123` |

A tela de login ainda **não valida** essas credenciais. Elas só aparecem como dica. A autenticação real será feita na Sprint 2.

---

## 📝 Campos dos formulários

### Artista (`cadastro_artista.html`)

| Campo | Nome (`name`) | Tipo | Obrigatório |
|---|---|---|---|
| Nome do Artista | `nome` | texto | ✅ |
| Gênero Musical | `genero` | texto | |
| País | `pais` | texto | |
| Foto do Artista | `imagem` | arquivo (imagem, JPG ou PNG, máx. 5 MB) | |

### Música (`cadastro_musica.html`)

| Campo | Nome (`name`) | Tipo | Obrigatório |
|---|---|---|---|
| Artista | `artista_id` | select | ✅ |
| Título | `titulo` | texto | ✅ |
| Álbum | `album` | texto | |
| Gênero | `genero` | texto | |
| Link do YouTube | `youtube_link` | url | ✅ |
| Capa do Álbum | `imagem_capa` | arquivo (imagem) | |

### Filtros da biblioteca (`listagem_musicas.html`)

Enviados por `GET`: `busca` (título, álbum ou artista), `artista` e `genero`.

---

## 🚀 Planejamento da Sprint 2

- [ ] Back-end em **PHP**
- [ ] Banco de dados com as tabelas `artistas` e `musicas`, ligadas pela chave estrangeira `artista_id`
- [ ] Login com sessão e `logout.php`
- [ ] Mostrar o nome do usuário logado no menu (hoje fixo como "admin")
- [ ] Salvar, editar e excluir artistas e músicas
- [ ] Upload de fotos de artistas e capas de álbuns
- [ ] Preencher listas e selects com dados do banco
- [ ] Filtros funcionando na biblioteca musical

---

## 🛠️ Tecnologias

- **HTML5**
- **CSS3** (layout com Flexbox e Grid)
- Previsto para a Sprint 2: **PHP** e **MySQL**

---

## 📄 Licença

Projeto desenvolvido para fins de estudo.
