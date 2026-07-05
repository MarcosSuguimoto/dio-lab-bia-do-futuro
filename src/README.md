# Código da Aplicação

A lista de arquivos utilizados no app e o código fonte estão no diretório poupa20. O arquivo com o código do app é o [app.py](app.py)

## Setup do Ollama
Linux

Abra o Terminal e execute:

curl -fsSL https://ollama.com/install.sh | sh

Aguarde o término da instalação.

## Estrutura

```
src/
├── app.py              # Aplicação principal (Streamlit)

```

## Exemplo de requirements.txt

```
streamlit
ollama
```

## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run app.py
```
