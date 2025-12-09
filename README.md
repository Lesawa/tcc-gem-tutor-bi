# Gem–Tutor BI (TCC – Sistemas de Informação)

Este repositório reúne os códigos-fonte e os prompts utilizados no protótipo **Gem–Tutor BI**, um tutor conversacional com IA generativa integrado conceitualmente ao Ambiente Virtual de Aprendizagem (AVA/LMS) e testado em um ambiente sandbox do Google Classroom.

O protótipo foi desenvolvido como parte do Trabalho de Conclusão de Curso (TCC) em Sistemas de Informação – Faculdade Impacta.

---

## 1. Objetivo do protótipo

O Gem–Tutor BI foi concebido como uma **camada de apoio ao estudo**, não como substituto de professor ou do AVA. Em termos gerais, o fluxo é:

1. O estudante escolhe:
   - um **objetivo de estudo** (começar, revisar, praticar);
   - um **formato preferido** (texto, vídeo);
2. A IA consulta uma lista **controlada de materiais** da disciplina de Business Intelligence;
3. O modelo seleciona até **3 sugestões** e devolve:
   - título do recurso;
   - link no AVA/Google Drive;
   - justificativa curta, alinhada ao objetivo de estudo.

Todo o desenho prioriza **uso responsável de IA generativa em EaD**, com:
- catálogo restrito ao conteúdo da disciplina;
- temperatura baixa (menor aleatoriedade);
- saída estruturada e auditável (JSON).

---

## 2. Arquitetura em alto nível

- **Fonte de dados**: materiais da disciplina de Business Intelligence organizados em diretório do Google Drive e vinculados a uma turma sandbox no Google Classroom.
- **Camada de aplicação**: scripts (por exemplo, Google Apps Script) responsáveis por:
  - organizar/consultar a lista de materiais elegíveis;
  - montar o prompt a partir das escolhas do estudante;
  - chamar o modelo de IA generativa (Gemini).
- **Camada de IA**: modelo Gemini, utilizado como camada de **seleção e explicação**, não como gerador livre de conteúdo.
- **Camada de interface**: interface conversacional (chat) onde o estudante envia suas solicitações e recebe as recomendações.

---

## 3. Estrutura do repositório

Sugestão de organização:

tcc-gem-tutor-bi/
├── prompts/
│   └── prompt_sistema_gem_tutor_bi.txt
└── README.md
