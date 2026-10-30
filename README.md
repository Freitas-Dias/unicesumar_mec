# Abaixo-assinado EaD UniCesumar
### Transparência e permanência nas regras de avaliação para estudantes matriculados até 2026

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)]()
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)]()
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)]()
[![Google Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-4285F4?logo=google&logoColor=white)]()
[![LGPD](https://img.shields.io/badge/Privacidade-LGPD-blue)]()

## Sobre o projeto

Plataforma digital de mobilização estudantil criada para reunir assinaturas de alunos e apoiadores de uma manifestação coletiva dirigida à Reitoria e à Direção da Educação a Distância da UniCesumar, com cópia à Ouvidoria.

A iniciativa busca promover transparência, previsibilidade e diálogo institucional diante das mudanças anunciadas nos critérios de avaliação dos cursos EaD a partir de 2027.

O objetivo central é solicitar que estudantes matriculados até 2026 tenham preservadas as regras de avaliação e a média mínima vigentes na data de sua matrícula, além de obter esclarecimentos oficiais sobre os fundamentos normativos das mudanças e suas regras de transição.

## Objetivos da iniciativa

1. **Permanência nas regras de avaliação:** reconhecimento da permanência dos critérios de avaliação e da média mínima vigentes na data de matrícula para estudantes matriculados até 2026.
2. **Transparência institucional:** publicação dos fundamentos normativos e administrativos que justificam as mudanças anunciadas para 2027.
3. **Regras de transição:** divulgação antecipada e por escrito dos procedimentos aplicáveis aos estudantes já matriculados.

## Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| Formulário de assinatura | Cadastro de nome, curso, polo e ano de ingresso. |
| Seleção de cursos | Lista de cursos com opção de informar outro. |
| Validação de dados | Verificação dos campos obrigatórios e consentimentos. |
| Contagem de assinaturas | Exibição do total de assinaturas registradas. |
| Estatísticas por curso | Distribuição das assinaturas por curso. |
| Controle local | Utilização do LocalStorage para evitar novas assinaturas no mesmo aparelho. |
| Consentimento LGPD | Registro da concordância com o tratamento dos dados. |
| Carta em PDF | Disponibilização do documento completo. |
| Responsividade | Adaptação para computadores, tablets e smartphones. |
| Tema automático | Suporte aos modos claro e escuro. |

## Tecnologias utilizadas

- HTML5 — estrutura da aplicação.
- CSS3 — identidade visual, responsividade e temas.
- JavaScript — validações, manipulação do DOM e comunicação com a API.
- Google Apps Script — backend para processamento das assinaturas.
- LocalStorage — controle local de assinaturas realizadas no dispositivo.

## Estrutura do projeto

```text
abaixo-assinado-ead/
│
├── index.html       # Página principal
├── carta.pdf        # Documento completo
└── README.md        # Documentação
```

## Integração com Google Apps Script

O projeto utiliza uma API publicada no Google Apps Script para conectar a interface ao processamento das assinaturas.

**URL da API:**

https://script.google.com/macros/s/AKfycbwHCYadTdScHoagAuuHenkjG-n0qwECVJAIhCEr59mYu3e9g1lvcsPDgUVEgPBlcM3i/exec

### Configuração

No arquivo `index.html`, a integração está configurada por meio da variável:

```javascript
const API_URL = "https://script.google.com/macros/s/AKfycbwHCYadTdScHoagAuuHenkjG-n0qwECVJAIhCEr59mYu3e9g1lvcsPDgUVEgPBlcM3i/exec";
```

### Comunicação com a API

A aplicação utiliza dois métodos HTTP:

**GET — Consulta das assinaturas**

Responsável por recuperar:
- Total de assinaturas;
- Quantidade de assinaturas por curso.

Formato esperado de resposta:

```json
{
  "total": 100,
  "cursos": {
    "Administração": 35,
    "Pedagogia": 40,
    "Fisioterapia": 25
  }
}
```

*Valores meramente ilustrativos.*

**POST — Registro de assinaturas**

Responsável por enviar os dados preenchidos no formulário:

```json
{
  "nome": "Nome do participante",
  "curso": "Fisioterapia",
  "polo": "Petrolina",
  "ano": 2025,
  "consentimento": true,
  "site": ""
}
```

O backend deverá validar os dados recebidos e retornar uma resposta JSON indicando sucesso ou erro.

## Como executar o projeto

### 1. Clonar o repositório

```bash
git clone URL_DO_REPOSITORIO
```

### 2. Acessar a pasta

```bash
cd abaixo-assinado-ead
```

### 3. Abrir a aplicação

Abra o arquivo `index.html` diretamente no navegador ou utilize a extensão Live Server do Visual Studio Code.

### 4. Verificar a integração

Com a API implantada e acessível, a aplicação poderá consultar as estatísticas e enviar novas assinaturas.

## Privacidade e LGPD

A aplicação considera os princípios da Lei Geral de Proteção de Dados Pessoais (Lei nº 13.709/2018).

Os dados coletados possuem a finalidade declarada de contabilizar as assinaturas e comprovar o apoio à manifestação coletiva.

Informações apresentadas no formulário:

- Responsável pela coleta: Ricardo Freitas.
- Contato: ricardocienciadedados@gmail.com.
- Base legal declarada: consentimento do titular (art. 7º, I, da LGPD).
- Direitos do titular: acesso, correção, exclusão e retirada do consentimento.

Os nomes dos participantes não são exibidos publicamente na interface.

A implementação deve contemplar medidas adequadas de segurança, controle de acesso, retenção e exclusão dos dados pessoais.

## Considerações importantes

Este projeto representa uma iniciativa independente de mobilização coletiva e diálogo institucional.

O abaixo-assinado não constitui ação judicial, não afirma antecipadamente a ilegalidade das mudanças anunciadas e não questiona a autonomia didático-científica da instituição.

Seu propósito é solicitar informações, previsibilidade e tratamento adequado aos estudantes já matriculados.

## Autor

**Ricardo Freitas**

Iniciativa independente de mobilização estudantil.

Contato: ricardocienciadedados@gmail.com

## Licença

Projeto desenvolvido para fins de mobilização estudantil e transparência institucional.
