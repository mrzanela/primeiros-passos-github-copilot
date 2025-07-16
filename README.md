# Primeiros Passos com o GitHub Copilot - Sistema de Atividades Extracurriculares

<img src="https://octodex.github.com/images/Professortocat_v2.png" align="right" height="200px" />

## Sobre o Projeto

Este é um projeto de demonstração que mostra como utilizar o GitHub Copilot para desenvolver um sistema de gerenciamento de atividades extracurriculares. O projeto foi construído usando Python com FastAPI para o backend e JavaScript puro para o frontend.

## Funcionalidades Implementadas

- ✅ Sistema de cadastro de atividades extracurriculares
- ✅ Interface web responsiva para visualização das atividades
- ✅ Funcionalidade de inscrição em atividades
- ✅ Funcionalidade de cancelamento de inscrição
- ✅ Validação de vagas disponíveis
- ✅ Feedback em tempo real para o usuário

## Tecnologias Utilizadas

- **Backend**: Python 3.13 com FastAPI
- **Frontend**: HTML, CSS e JavaScript vanilla
- **Desenvolvimento**: GitHub Copilot

## Como Executar o Projeto

1. Clone o repositório:
```bash
git clone https://github.com/mrzanela/primeiros-passos-github-copilot.git
cd primeiros-passos-github-copilot
```

2. Instale as dependências:
```bash
pip install -r requirements.txt
```

3. Execute o servidor:
```bash
python -m uvicorn src.app:app --reload
```

4. Acesse no navegador:
```
http://localhost:8000
```

## Estrutura do Projeto

```
src/
  ├── app.py           # Backend da aplicação
  ├── static/         
  │   ├── app.js      # Lógica do frontend
  │   ├── index.html  # Página principal
  │   └── styles.css  # Estilos CSS
  └── README.md       # Documentação
```

## Aprendizados com o GitHub Copilot

Este projeto demonstra como o GitHub Copilot pode acelerar o desenvolvimento:

- 🤖 Geração automática de código repetitivo
- 📝 Sugestões contextuais inteligentes
- 🔄 Refatoração e melhorias de código
- 🐛 Ajuda na identificação e correção de bugs

## Como Contribuir

1. Faça um fork do repositório
2. Crie uma branch para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. Faça commit das suas alterações (`git commit -am 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

&copy; 2025 GitHub &bull; [Código de Conduta](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [Licença MIT](https://gh.io/mit)



```mermaid
flowchart TD
  subgraph Cadastro[Cadastro de Atividades]
    CAD1[Usuário envia dados da atividade]
    CAD2[Valida campos obrigatórios]
    CAD3[Verifica vagas disponíveis]
    CAD4[Salva atividade]
    CAD5[Retorna confirmação]
    CAD1 --> CAD2 --> CAD3 --> CAD4 --> CAD5
  end

  subgraph Inscrição[Inscrição em Atividade]
    INS1[Usuário solicita inscrição]
    INS2[Valida se atividade existe]
    INS3[Verifica vagas disponíveis]
    INS4[Verifica se já está inscrito]
    INS5[Adiciona participante]
    INS6[Retorna sucesso ou erro]
    INS1 --> INS2 --> INS3 --> INS4
    INS4 -- "Não inscrito" --> INS5 --> INS6
    INS4 -- "Já inscrito" --> INS6
    INS3 -- "Sem vagas" --> INS6
  end

  subgraph Cancelamento[Cancelamento de Inscrição]
    CAN1[Usuário solicita cancelamento]
    CAN2[Valida se atividade existe]
    CAN3[Verifica se está inscrito]
    CAN4[Remove participante]
    CAN5[Retorna sucesso ou erro]
    CAN1 --> CAN2 --> CAN3
    CAN3 -- "Inscrito" --> CAN4 --> CAN5
    CAN3 -- "Não inscrito" --> CAN5
  end

  subgraph Listagem[Listagem de Atividades]
    LIST1[Usuário solicita lista]
    LIST2[Backend retorna lista de atividades]
    LIST1 --> LIST2
  end

  subgraph Detalhes[Detalhes de Atividade]
    DET1[Usuário solicita detalhes]
    DET2[Backend retorna detalhes]
    DET1 --> DET2
  end

  %% Relações entre endpoints
  CAD5 -. Atualiza .-> LIST2
  INS6 -. Atualiza .-> DET2
  CAN5 -. Atualiza .-> DET2
```
