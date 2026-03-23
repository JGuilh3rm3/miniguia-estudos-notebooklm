# Caderno Temático: Fundamentos de Cyber Security com IA

Desafio de Projeto - DIO | Bootcamp Cyber Security Fundamentals

---

## Autor

**João Guilherme Andrade**  
Estudante de Análise e Desenvolvimento de Sistemas - UNIP  
Cursando: Bootcamp Cyber Security Fundamentals - DIO (2026)  
[LinkedIn](https://linkedin.com/in/joaoguilhermeandrade) | [GitHub](https://github.com/joaoguilherme)

---

## Contexto e Objetivos

### Sobre o projeto

Esse projeto surgiu como forma de organizar os estudos do Bootcamp de Cyber Security da DIO. A ideia foi usar o conhecimento adquirido em engenharia de prompt dentro do Claude e NotebookLM para criar um caderno temático com fontes reais da área, testando como a IA responde quando você define bem o contexto e as perguntas.

### O que é o NotebookLM?

O [NotebookLM](https://notebooklm.google.com/) é uma ferramenta do Google que deixa você fazer upload de PDFs, textos e links, e depois conversar com eles. Diferente de um chatbot normal, ele responde baseado nas fontes que você carregou, o que ajuda bastante a evitar respostas genéricas ou inventadas.

### Objetivos de estudo

| # | Objetivo | Status |
|---|----------|--------|
| 1 | Entender os fundamentos de Redes e o modelo OSI | Concluido |
| 2 | Estudar IAM (Identity and Access Management) | Concluido |
| 3 | Ver as etapas de um Pentest e as ferramentas principais | Em andamento |
| 4 | Entender TPCRM e frameworks como NIST CSF e ISO 27001 | Em andamento |

---

## Curadoria de Fontes

As fontes abaixo foram escolhidas por serem gratuitas, abertas e relevantes para o tema. Todas foram carregadas no NotebookLM.

### Fonte 1 - NIST Cybersecurity Framework (CSF) 2.0
- **Tipo:** PDF oficial
- **Orgao:** National Institute of Standards and Technology (NIST)
- **Link:** [https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf)
- **Por que escolhi:** É o framework mais citado quando o assunto é gestão de riscos em segurança. Cobre as funções GOVERN, IDENTIFY, PROTECT, DETECT, RESPOND e RECOVER.

### Fonte 2 - OWASP Top 10 (2021)
- **Tipo:** Documento web / PDF
- **Orgao:** Open Web Application Security Project (OWASP)
- **Link:** [https://owasp.org/www-project-top-ten/](https://owasp.org/www-project-top-ten/)
- **Por que escolhi:** Lista as 10 vulnerabilidades mais comuns em aplicações web. É referência tanto pra quem trabalha com segurança ofensiva quanto defensiva.

### Fonte 3 - Cartilha de Segurança (CERT.br)
- **Tipo:** Cartilha em PDF
- **Orgao:** Centro de Estudos, Resposta e Tratamento de Incidentes de Segurança no Brasil
- **Link:** [https://cartilha.cert.br/livro/cartilha-seguranca-internet.pdf](https://cartilha.cert.br/livro/cartilha-seguranca-internet.pdf)
- **Por que escolhi:** Fonte brasileira, bem didática e com um bom panorama geral sobre segurança. Útil pra contextualizar o cenário nacional.

### Fonte 4 - The Linux Command Line (William Shotts)
- **Tipo:** Livro gratuito em PDF
- **Autor:** William Shotts
- **Link:** [https://sourceforge.net/projects/linuxcommand/files/TLCL/19.01/TLCL-19.01.pdf](https://sourceforge.net/projects/linuxcommand/files/TLCL/19.01/TLCL-19.01.pdf)
- **Por que escolhi:** Linux é o ambiente padrão em Cyber Security. Sem saber linha de comando fica difícil usar o Kali, analisar logs ou automatizar qualquer coisa.

### Fonte 5 - Penetration Testing (Georgia Weidman)
- **Tipo:** Trechos disponíveis gratuitamente
- **Autor:** Georgia Weidman
- **Link:** [https://nostarch.com/pentesting](https://nostarch.com/pentesting)
- **Por que escolhi:** Boa referência prática de pentest. Ajuda a conectar a teoria com uma metodologia real de testes.

---

## Engenharia de Prompts e Cicatrizes

Aqui documento as perguntas que testei no NotebookLM, o que deu certo, o que não deu e o que aprendi com cada tentativa.

---

### Prompt 1 - Mapeamento inicial

**Objetivo:** Ter uma visão geral do que as fontes cobrem

**Prompt:**
```
Com base nas fontes carregadas, quais são os 5 temas mais recorrentes
relacionados à segurança defensiva? Liste com uma frase explicativa para cada.
```

**Resultado:** O NotebookLM identificou: gestão de identidade e acesso, resposta a incidentes, controle de vulnerabilidades web, segurança em Linux e frameworks de conformidade. Cada item veio com referência da fonte.

**O que funcionou:** Pedir um número fixo (5) e pedir explicação curta forçou o modelo a ser mais objetivo.

**Dificuldade:** Na primeira tentativa não pedi a frase explicativa e o retorno foi só uma lista de títulos sem contexto nenhum.

---

### Prompt 2 - Comparação entre frameworks

**Objetivo:** Entender as diferenças práticas entre NIST CSF e ISO 27001

**Prompt v1 (não funcionou bem):**
```
Qual é melhor: NIST CSF ou ISO 27001?
```

**Problema:** A resposta foi genérica demais e o modelo avisou que a Fonte 5 não tinha informações sobre ISO 27001.

**Prompt v2 (funcionou):**
```
Com base exclusivamente no documento do NIST CSF 2.0 carregado,
explique as 6 funções do framework e como elas se relacionam entre si.
Em seguida, indique quais delas têm maior sobreposição conceitual com
os controles de acesso descritos na Cartilha CERT.br.
```

**Resultado:** Resposta bem estruturada com as 6 funções e o cruzamento com os conceitos de autenticação da cartilha CERT.br.

**Aprendizado:** Comparações funcionam melhor quando você diz explicitamente quais fontes usar e evita perguntas abertas demais.

---

### Prompt 3 - Caso prático de incidente

**Objetivo:** Conectar a teoria de IAM com um cenário real

**Prompt:**
```
Imagine um cenário em que uma empresa de e-commerce sofre uma violação
de dados por credenciais comprometidas. Com base nas fontes carregadas,
elabore um plano de resposta ao incidente usando a estrutura do NIST CSF
e inclua quais controles de IAM deveriam ter prevenido o ataque.
```

**Resultado:** O modelo gerou um cenário coerente, citando as funções DETECT e RESPOND do NIST e os controles de MFA e RBAC da cartilha CERT.br. Mas inventou um "Artigo 3.2" que não existe na fonte.

**Troubleshooting:** Quando vi a citação estranha, pedi: *"Mostre a citação exata da fonte que embasa o Artigo 3.2 mencionado."* O modelo reconheceu o erro e corrigiu.

**Regra que aprendi:** Sempre questionar referências numéricas específicas. O modelo confirma quando a fonte não existe se você perguntar direto.

---

### Prompt 4 - Questões de revisão

**Objetivo:** Gerar material pra estudar por active recall

**Prompt:**
```
Crie 10 perguntas de múltipla escolha, nível intermediário, sobre os
temas das fontes carregadas. Para cada pergunta, inclua: 4 alternativas,
a resposta correta e uma explicação de 2 linhas baseada na fonte de origem.
```

**Resultado:** 10 questões cobrindo OWASP Top 10, NIST CSF e Linux. As explicações vieram com referência de seção das fontes.

**Dica:** Especificar nível (iniciante/intermediário/avançado) e o formato exato faz bastante diferença na qualidade da saída.

---

### Prompt 5 - Extração de termos para o glossário

**Prompt:**
```
Extraia das fontes carregadas todos os termos técnicos relevantes para
Cyber Security. Para cada termo: forneça a definição conforme a fonte,
indique em qual documento o termo aparece e classifique em uma das
categorias: [Redes | IAM | Pentest | Frameworks | Criptografia].
```

**Resultado:** Lista com os principais termos categorizados e com definições rastreáveis. Virou a base do glossário abaixo.

---

## Miniguia de Estudo

### 1. Resumos por tema

#### Redes e Modelo OSI

O modelo OSI divide a comunicação em rede em 7 camadas. As mais relevantes para segurança são:

- **Camada 7 (Aplicação):** onde operam HTTP, HTTPS, DNS e FTP. É o principal alvo do OWASP Top 10.
- **Camada 4 (Transporte):** TCP e UDP. Ataques de SYN Flood exploram o handshake TCP. Portas são a base do reconhecimento em pentest.
- **Camada 3 (Rede):** roteamento IP. Ataques de spoofing ocorrem nessa camada.

Portas que vale memorizar:

| Porta | Servico | Relevancia em Seguranca |
|-------|---------|------------------------|
| 22 | SSH | Alvo comum de brute force |
| 80/443 | HTTP/HTTPS | Ataques web (OWASP) |
| 53 | DNS | DNS Poisoning |
| 3389 | RDP | Exposicao comum em ransomware |
| 3306 | MySQL | Injecao SQL, BD exposto |

---

#### IAM - Identity and Access Management

IAM é o conjunto de politicas e tecnologias que controlam quem acessa o que dentro de um sistema.

Os três pilares (AAA):
- **Autenticação (AuthN):** verificar quem é o usuário (senha, MFA, biometria)
- **Autorização (AuthZ):** o que ele pode fazer (RBAC, ABAC, PoLP)
- **Accounting:** registrar e auditar o que foi feito (logs, SIEM)

**Principio do Menor Privilégio (PoLP):** cada usuário recebe só o acesso mínimo necessário pra exercer sua função. É uma das medidas com maior impacto na redução da superficie de ataque.

---

#### Pentest - Fases e Metodologia

Um teste de penetração segue uma sequência definida:

1. **Reconhecimento (Recon):** coleta de informações sobre o alvo, passiva (OSINT) e ativa
2. **Varredura (Scanning):** descoberta de portas, serviços e versões (Nmap, Nikto)
3. **Exploração:** tentativa de acesso usando vulnerabilidades conhecidas (Metasploit, CVEs)
4. **Pós-exploração:** escalada de privilégios, movimentação lateral, persistência
5. **Relatório:** documentação com CVSS Score e recomendações de correção

---

#### OWASP Top 10 (2021)

| # | Vulnerabilidade | Exemplo |
|---|----------------|---------|
| A01 | Quebra de Controle de Acesso | Acessar dados de outro usuário pela URL |
| A02 | Falhas Criptograficas | Senhas em MD5, dados trafegando sem HTTPS |
| A03 | Injecao | SQL Injection, Command Injection |
| A07 | Falhas de Autenticacao | Sem MFA, sessões que nao expiram |
| A09 | Falhas em Logging e Monitoramento | Ataques passando despercebidos por dias |

---

### 2. Glossário

| Termo | Definicao | Categoria |
|-------|-----------|-----------|
| Attack Surface | Conjunto de pontos de entrada que um atacante pode explorar | Pentest |
| RBAC | Controle de acesso baseado em funcoes/cargos | IAM |
| ABAC | Controle de acesso baseado em atributos contextuais | IAM |
| PoLP | Principio do Menor Privilegio | IAM |
| MFA | Autenticacao com dois ou mais fatores | IAM |
| CVE | Identificador unico de vulnerabilidades conhecidas | Pentest |
| CVSS | Pontuacao de severidade de vulnerabilidades (0 a 10) | Pentest |
| Zero Trust | Modelo que nao confia em nenhuma entidade por padrao, nem dentro da rede | Frameworks |
| SIEM | Ferramenta de correlacao e analise de logs de seguranca | Redes |
| OSINT | Coleta de informacoes a partir de fontes publicas | Pentest |
| Hashing | Funcao unidirecional que gera um digest de dados (SHA-256, bcrypt) | Criptografia |
| SSL/TLS | Protocolos de criptografia para comunicacao segura | Criptografia |
| PKI | Infraestrutura para emissao e gestao de certificados digitais | Criptografia |
| IDS/IPS | Sistemas que detectam e/ou bloqueiam intrusoes na rede | Redes |
| WAF | Firewall para aplicacoes web, filtra requisicoes maliciosas | Redes |
| NIST CSF | Framework do NIST para gestao de riscos em Cyber Security | Frameworks |
| ISO 27001 | Norma internacional para gestao de seguranca da informacao | Frameworks |
| TPCRM | Gestao de riscos ciberneticos de fornecedores terceiros | Frameworks |
| Lateral Movement | Movimentacao do atacante dentro da rede apos comprometimento inicial | Pentest |
| Privilege Escalation | Ganho de privilegios alem do nivel de acesso inicial | Pentest |
| Social Engineering | Manipulacao psicologica para obter acesso ou informacoes | Pentest |
| DLP | Tecnologia que previne o vazamento de dados | Frameworks |
| SOC | Time responsavel por monitorar e responder a incidentes de seguranca | Frameworks |
| TTPs | Taticas, Tecnicas e Procedimentos usados por atacantes | Pentest |

---

### 3. Prompts reutilizáveis

Esses prompts foram testados no NotebookLM e podem ser reaproveitados em qualquer caderno sobre Cyber Security.

**Para revisão ativa:**
```
Crie um quiz de 10 questões de múltipla escolha (nível [iniciante/intermediário/avançado])
sobre [TEMA]. Para cada questão inclua: 4 alternativas, gabarito e explicação de 2 linhas
citando a fonte de origem.
```

**Para mapear o que ainda falta estudar:**
```
Analise as fontes carregadas e identifique os 3 temas que estão menos cobertos
em detalhes técnicos. Para cada tema, sugira uma pergunta de pesquisa que eu
deveria buscar em fontes complementares.
```

**Para criar casos práticos:**
```
Com base nas fontes, crie um cenário realista de [TIPO DE ATAQUE/INCIDENTE]
em uma empresa de [SETOR]. Descreva: (1) como o ataque ocorreu, (2) quais
controles falharam segundo as fontes, (3) como o NIST CSF guiaria a resposta.
```

**Para comparar conceitos:**
```
Compare os conceitos de [CONCEITO A] e [CONCEITO B] com base exclusivamente
nas fontes carregadas. Use uma tabela com as colunas: Definição, Quando usar,
Limitações, Fonte de referência.
```

**Para montar glossário:**
```
Extraia das fontes todos os termos técnicos de [TEMA]. Para cada termo:
definição conforme a fonte, documento de origem e categoria em:
[Redes | IAM | Pentest | Frameworks | Criptografia].
```

**Para checar se uma citação é real:**
```
Você mencionou [CITAÇÃO/FATO]. Mostre a transcrição exata do trecho da fonte
que embasa essa afirmação, incluindo o nome do documento e a localização aproximada.
```

**Para montar um plano de estudo:**
```
Meu objetivo é [OBJETIVO]. Com base nas fontes, crie um plano de estudo de 4 semanas
com: tópico semanal, perguntas-chave e uma atividade prática que eu possa fazer offline.
```

---

## Conclusão

O NotebookLM foi útil principalmente para cruzar informações entre as fontes e gerar material de revisão. O ponto mais importante que aprendi é que a qualidade da resposta depende diretamente da qualidade da pergunta. Prompt vago, resposta vaga.

Também vale tomar cuidado com citações numéricas específicas. O modelo eventualmente inventa referências que não existem nas fontes. Pedir pra ele mostrar a citação exata resolve na hora.

O processo de testar, errar e ajustar o prompt foi o que mais me ensinou nesse projeto.

---

## Ferramentas usadas

- [NotebookLM](https://notebooklm.google.com/)
- [GitHub](https://github.com)
- [DIO](https://dio.me)

---

*Bootcamp Cyber Security Fundamentals - DIO, 2026*
