# 🤖 AutoTDD — IA gerando testes, documentação e análise de segurança para Delphi

**GitHub Action** que usa IA para gerar **testes unitários**, **documentação** e **análise de segurança** em código **Delphi**, direto no pipeline. Criado em 2023, quando levar IA para o ciclo de desenvolvimento ainda era novidade.

![Delphi](https://img.shields.io/badge/Delphi-B22222?style=for-the-badge&logo=delphi&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)

## ⚙️ Como funciona

```
push na main ──► GitHub Action ──► script Go lê os .pas alterados no commit
                                        │
                                        ▼
                         encontra as tags //<TEST>, //<DOCUMENT>, //<SECURITY>
                                        │
                                        ▼
                         envia o trecho para a API da OpenAI
                                        │
                                        ▼
                  insere a resposta no próprio arquivo e faz commit automático
```

## 🏷️ Tags

Envolva o trecho de código Delphi com a tag da ação desejada:

```pascal
//<TEST>
function Somar(A, B: Integer): Integer;
begin
  Result := A + B;
end;
//</TEST>
```

| Tag | O que a IA gera |
|---|---|
| `//<TEST>` | Método de teste unitário para o trecho |
| `//<DOCUMENT>` | Comentário de documentação |
| `//<SECURITY>` | Análise de segurança com sugestões de melhoria |

## 🚀 Como usar

1. Cadastre o secret `OPENAI_API_KEY` em **Settings → Secrets and variables → Actions**
2. Adicione as tags no código Delphi e faça push na `main`
3. A Action processa os arquivos `.pas` alterados e comita o resultado

## 📁 Estrutura

- `.github/workflows/` — pipeline da Action
- `main.go` — script que encontra as tags, chama a IA e reescreve o arquivo
- `src/` — projeto Delphi de exemplo (login com Model/Controller)

---

Desenvolvido por **Yuri Bertoldi** — [LinkedIn](https://www.linkedin.com/in/yuri-bulh%C3%B5es-bertoldi-b62459180/)
