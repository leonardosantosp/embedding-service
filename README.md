# embedding-service

Microservice for generating text embeddings using Sentence Transformers, optimized for semantic search applications.

## 📌 Requisitos

- Python 3.8+

- pip

## ⚙️ Instalação

- Clone o repositório:

```bash
  git clone [seu-repositorio]
```

```bash
  cd embedding-service
```

### Instale as dependências:

```bash
  pip install fastapi
  pip install sentence_transformers
  pip install pydantic
```

## 🚀 Como Executar

### Inicie o serviço com:

```bash
  python3 app/main.py
```

#### O serviço estará disponível em:

`http://localhost:8000`

## 🌐 Endpoints

### 🔍 Verificar saúde do serviço

`GET http://localhost:8000/health`

#### Resposta:

```json
{
  "status": "healthy",
  "model": "all-MiniLM-L6-v2"
}
```

### ✨ Gerar embeddings

`POST http://localhost:8000/embed`

#### Corpo da requisição:

```json
{
  "text": "texto que vira embedding"
}
```

#### Resposta:

```json
  {
   "embedding": [0.12, -0.34, ...],
   //   Array de 384 dimensões
    "model": "all-MiniLM-L6-v2",
    "dims": 384
  }
```

## 📚 Exemplo de Uso

### Com cURL:

```bash
  curl -X POST http://localhost:8000/embed \
  -H "Content-Type: application/json" \
  -d '{"text":"exemplo de texto para embedding"}'
```

## 🛠️ Tecnologias Utilizadas

- FastAPI - Framework web

- Sentence Transformers - Modelos de embeddings

- PyTorch - Backend para inferência
