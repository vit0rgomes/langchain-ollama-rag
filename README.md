# Sistema RAG (Retrieval-Augmented Generation) com Ollama

Sistema de perguntas e respostas baseado em documentos PDF usando embeddings locais e modelos de linguagem do Ollama.

## Visão Geral

Este projeto implementa um sistema RAG (Retrieval-Augmented Generation) que permite fazer perguntas sobre documentos PDF. O sistema:

1. Carrega e processa PDFs da pasta `base/`
2. Divide os documentos em chunks
3. Gera embeddings usando o modelo `mxbai-embed-large` do ollama
4. Armazena os vetores no banco Chroma
5. Responde perguntas buscando contexto relevante nos documentos disponibilizados

---

### Softwares Utilizados

- **Python 3.12+**
- **Ollama** instalado e rodando ([Download](https://ollama.com/download))

### Modelos do Ollama

#### Modelo de embeddings (1024 dimensões)
- mxbai-embed-large

#### Modelo de chat
- llama3.2

**Obs: O Ollama precisa estar rodando esses dois modelos**

### Bibliotecas Python utilizadas

```bash
pip install python-dotenv langchain langchain-core langchain-ollama \
            langchain-community langchain-chroma chromadb ollama pypdf
```

---

## Estrutura do Projeto

```
projeto/
├── base/                    # 📁 PDFs de entrada
│   ├── documento1.pdf
│   └── documento2.pdf
├── db/                      # Banco vetorial Chroma (gerado)
│   └── ...
├── criar_db.ipynb           # Script para criar o banco
├── main.ipynb               # Script principal (perguntas)
├── .env                     # Variáveis de ambiente (se precisar)
└── README.md                # 📖 README
```

---

## Como funciona?

### Adicione seus PDFs

Na pasta `base/` e coloque seus arquivos PDF:

```
projeto/
├── base/
│   ├── documento1.pdf
│   ├── documento2.pdf
│   └── ...
├── criar_db.ipynb
└── main.ipynb
```

---

### Crie o Banco de Dados

Execute o notebook `criar_db.ipynb`:

```python
# Executa todas as células do criar_db.ipynb
# Isso irá:
# 1. Carregar PDFs da pasta base/
# 2. Dividir em chunks de 2000 caracteres
# 3. Gerar embeddings com mxbai-embed-large
# 4. Salvar no banco Chroma (db/)
```

**Saída esperada:** <br>
Na última célula você verá algo como
`Banco de dados Criado`
se o banco tiver sido criado


### Faça suas Perguntas

Execute o notebook `main.ipynb`:

```python
# Executa a função perguntar()
# Digite sua pergunta e pressione Enter
```
## Conclusão

Este sistema RAG oferece uma solução completa e 100% local para consulta inteligente de documentos PDF, sem depender de APIs externas pagas. Ao combinar o poder dos embeddings do Ollama com o banco vetorial Chroma

---

## 🔗 Links Úteis

- [Ollama](https://ollama.com/)
- [LangChain Docs](https://python.langchain.com/)
- [Chroma DB](https://www.trychroma.com/)
- [Modelos Ollama](https://ollama.com/library)

---
