# Abaixo-assinado EaD UniCesumar
### Transparência e permanência nas regras de avaliação para estudantes matriculados até 2026

[![Status](https://img.shields.io/badge/Status-Em%20desenvolvimento-yellow)]()
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)]()
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)]()
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)]()
[![LGPD](https://img.shields.io/badge/Privacidade-LGPD-blue)]()

## Sobre o projeto

Este projeto consiste em uma plataforma digital de mobilização estudantil criada para reunir assinaturas de alunos e apoiadores de uma manifestação coletiva dirigida à Reitoria e à Direção da Educação a Distância da UniCesumar, com cópia à Ouvidoria da instituição.

A iniciativa busca promover transparência, previsibilidade e diálogo institucional diante das mudanças anunciadas nos critérios de avaliação dos cursos EaD a partir de 2027.

O objetivo central é solicitar que os estudantes matriculados até 2026 tenham preservadas as regras de avaliação e a média mínima vigentes na data de sua matrícula, além de obter esclarecimentos oficiais sobre os fundamentos normativos das mudanças e suas regras de transição.

**Acesse a carta completa:** `carta.pdf`.

## Objetivos da iniciativa

O abaixo-assinado apresenta três reivindicações principais:

1. **Permanência nas regras de avaliação:** reconhecimento da permanência dos critérios de avaliação e da média mínima vigentes na data de matrícula para estudantes matriculados até 2026.
2. **Transparência institucional:** publicação dos fundamentos normativos e administrativos que justificam as mudanças anunciadas para 2027.
3. **Regras de transição:** divulgação antecipada e por escrito dos procedimentos aplicáveis aos estudantes já matriculados.

A iniciativa também apresenta uma alternativa para a hipótese de manutenção das novas regras, solicitando critérios compatíveis com o modelo anteriormente praticado e um período de adaptação.

## Funcionalidades

A plataforma foi desenvolvida para oferecer uma experiência simples, acessível e responsiva.

| Funcionalidade | Descrição |
|---|---|
| Formulário de assinatura | Cadastro de nome completo, curso, polo e ano de ingresso. |
| Seleção de cursos | Lista de cursos com opção de informar outra graduação. |
| Validação de dados | Verificação dos campos obrigatórios e das declarações de consentimento. |
| Contagem de assinaturas | Exibição da quantidade total de assinaturas registradas. |
| Estatísticas por curso | Visualização da distribuição de assinaturas por curso. |
| Proteção contra duplicidade local | Utilização do armazenamento local do navegador para evitar novas assinaturas no mesmo aparelho. |
| Consentimento LGPD | Registro da concordância com o tratamento dos dados pessoais. |
| Documento oficial | Disponibilização da carta completa em PDF para consulta e download. |
| Layout responsivo | Adaptação para computadores, tablets e smartphones. |
| Tema automático | Suporte aos modos claro e escuro conforme a preferência do sistema operacional. |

## Tecnologias utilizadas

O projeto utiliza tecnologias fundamentais do desenvolvimento web:

- **HTML5:** estruturação e organização dos elementos da página.
- **CSS3:** estilização, responsividade, identidade visual e adaptação aos temas claro e escuro.
- **JavaScript:** validações, manipulação do DOM, processamento do formulário e comunicação com a API.
- **Google Apps Script:** integração prevista para recebimento e processamento das assinaturas.
- **LocalStorage:** armazenamento local de informações para controle de assinaturas realizadas no dispositivo.

## Estrutura do projeto

```text
abaixo-assinado-ead/
│
├── index.html       # Página principal da aplicação
├── carta.pdf        # Documento completo do abaixo-assinado
└── README.md        # Documentação do projeto
```

## Como funciona

O funcionamento da aplicação está organizado em quatro etapas:

**1. Preenchimento do formulário**

O participante informa:
- Nome completo;
- Curso;
- Polo;
- Ano de ingresso.

**2. Validação e consentimento**

Antes do envio, a aplicação verifica os campos obrigatórios e exige duas declarações:

- Confirmação de que o participante possui 18 anos ou mais e é aluno ou apoiador da causa.
- Consentimento para o tratamento dos dados pessoais, conforme a LGPD.

**3. Envio da assinatura**

Os dados são enviados por meio de uma requisição HTTP POST para uma API configurada no Google Apps Script.

**4. Atualização das estatísticas**

A aplicação consulta a API por meio de uma requisição HTTP GET e apresenta:

- Número total de assinaturas;
- Quantidade de assinaturas por curso;
- Representação visual da distribuição dos participantes.

## Configuração e execução

### 1. Clonar o repositório

```bash
git clone URL_DO_REPOSITORIO
```

### 2. Acessar a pasta

```bash
cd abaixo-assinado-ead
```

### 3. Configurar a integração com a API

No arquivo `index.html`, localize:

```javascript
const API_URL = "COLE_AQUI_A_URL_DO_APPS_SCRIPT";
```

Substitua o valor pela URL de implantação do Google Apps Script responsável pelo processamento das assinaturas.

**Importante:** o código disponibilizado contém apenas a interface de integração. O backend do Google Apps Script precisa ser desenvolvido, configurado e implantado separadamente.

A API deverá atender aos seguintes contratos:

- **GET:** retornar os dados estatísticos no formato JSON, incluindo `total` e `cursos`.
- **POST:** receber os dados da assinatura, validar as informações e retornar um resultado indicando sucesso ou erro.

### 4. Executar localmente

Após configurar os arquivos, abra o `index.html` em um navegador ou utilize a extensão Live Server do Visual Studio Code.

Para o funcionamento completo, a API deverá estar publicada e acessível.

## Privacidade e proteção de dados

A aplicação foi estruturada considerando princípios da Lei Geral de Proteção de Dados Pessoais (LGPD — Lei nº 13.709/2018).

As informações coletadas possuem a finalidade declarada de contabilizar as assinaturas e comprovar o apoio à manifestação coletiva.

O formulário informa:

- Responsável pela coleta: Ricardo Freitas.
- Contato: ricardocienciadedados@gmail.com.
- Base legal declarada: consentimento do titular (art. 7º, I, da LGPD).
- Direito de acesso, correção e exclusão dos dados.

Os nomes dos participantes não são exibidos publicamente na interface.

**Observação:** a implementação definitiva deve contemplar também medidas de segurança no armazenamento, controle de acesso, retenção e exclusão dos dados. A configuração efetiva do compartilhamento das assinaturas e do prazo de guarda deve ser definida e informada aos participantes antes da coleta.

## Considerações importantes

Este projeto representa uma iniciativa de mobilização coletiva e diálogo institucional.

O abaixo-assinado não constitui ação judicial, não afirma antecipadamente a ilegalidade das mudanças anunciadas e não questiona a autonomia didático-científica da instituição.

Seu propósito é solicitar informações, previsibilidade e tratamento adequado aos estudantes já matriculados.

## Autor

**Ricardo Freitas**

Iniciativa independente de mobilização estudantil.

Contato: ricardocienciadedados@gmail.com

## Licença

Projeto desenvolvido para fins de mobilização estudantil e transparência institucional.

A utilização, reprodução ou adaptação do código deve preservar a finalidade informativa da iniciativa e os cuidados relacionados à proteção dos dados pessoais.
