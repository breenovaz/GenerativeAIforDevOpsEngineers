# PR Review IaC - Análise Automatizada de Pull Requests de Infrastructure as Code

## 📋 Sobre o Projeto

Este projeto de MBA apresenta uma solução inovadora para análise automatizada de Pull Requests (PRs) de Infrastructure as Code (IaC) utilizando Terraform e CloudFormation. O foco principal é a implementação progressiva de prompts e garantia de segurança contra ataques de injeção de prompts (Prompt Injection).

### Objetivo

Desenvolver um sistema inteligente capaz de:
- ✅ Analisar automaticamente mudanças de IaC em PRs
- ✅ Identificar riscos de segurança e configurações inapropriadas
- ✅ Evitar vulnerabilidades de injeção de prompts (Prompt Injection)
- ✅ Fornecer feedback estruturado e acionável

---

## 🏗️ Estrutura do Projeto

```
projetosk8s/
├── docs/                          # Documentação completa
│   ├── 01_INTRODUCAO.md
│   ├── 02_FUNDAMENTACAO_TEORICA.md
│   ├── 03_METODOLOGIA.md
│   ├── 04_IMPLEMENTACAO.md
│   └── 05_CONCLUSOES.md
├── prompts/                       # Versões progressivas de prompts
│   ├── v1_basico.md              # Versão básica
│   ├── v2_melhorado.md           # Versão com segurança intermediária
│   ├── v3_robusto.md             # Versão com proteção completa
│   └── guidelines.md             # Diretrizes de design
├── terraform_examples/            # Exemplos de código Terraform
│   ├── exemplo_seguro.tf
│   ├── exemplo_inseguro.tf
│   └── exemplo_melhorado.tf
├── pr_samples/                    # Exemplos de PRs para teste
│   ├── pr_valido.json
│   ├── pr_malicioso_injection.json
│   └── pr_complexo.json
├── security_tests/                # Testes de segurança
│   ├── test_prompt_injection.py
│   ├── test_security_bypass.py
│   └── test_results.md
├── main.tf                        # Arquivo principal (existente)
└── README.md                      # Este arquivo
```

---

## 📚 Conteúdo dos Diretórios

### `/docs` - Documentação Técnica
Contém toda a documentação acadêmica do projeto, incluindo:
- Introdução e contexto
- Fundamentação teórica
- Metodologia de pesquisa
- Detalhes de implementação
- Conclusões e recomendações

### `/prompts` - Prompts Versões
Implementação progressiva de 3 versões de prompts:

1. **V1 - Básico**: Funcionalidade essencial sem proteções avançadas
2. **V2 - Melhorado**: Adição de validações e primeiras proteções
3. **V3 - Robusto**: Proteção completa contra injection e sanitização

### `/terraform_examples` - Exemplos Terraform
Casos de uso reais com:
- ✅ Código seguro
- ❌ Código inseguro (vulnerável)
- 🔧 Código melhorado

### `/pr_samples` - Amostras de PR
Casos de teste includindo:
- PRs legítimos
- PRs maliciosos com tentativa de prompt injection
- PRs complexos com múltiplas mudanças

### `/security_tests` - Testes de Segurança
Scripts Python para validar:
- Resistência a prompt injection
- Bypass de validações
- Relatórios de resultados

---

## 🚀 Como Usar

### 1. Revisar a Documentação
```bash
cd docs/
# Ler os arquivos em ordem sequencial
```

### 2. Entender as Versões de Prompt
```bash
cd prompts/
# Comparar as 3 versões
# v1_basico.md → v2_melhorado.md → v3_robusto.md
```

### 3. Testar com Exemplos
```bash
cd terraform_examples/
# Analisar os três tipos de arquivo
```

### 4. Executar Testes de Segurança
```bash
cd security_tests/
python test_prompt_injection.py
python test_security_bypass.py
```

---

## 🔒 Segurança - Proteção contra Prompt Injection

### Níveis de Proteção Implementados

| Nível | Versão | Proteções |
|-------|--------|-----------|
| Básico | V1 | Nenhuma proteção específica |
| Intermediário | V2 | Validação de input, Sanitização básica |
| Robusto | V3 | Sanitização completa, Detecção de padrões maliciosos, Rate limiting |

### Exemplos de Ataques Testados

1. **Injeção Direta**: Mudança de instruções via comentários
2. **Codificação**: Base64, URL encoding
3. **Bypass de Validação**: Caracteres especiais e escape
4. **Prompt Smuggling**: Inserção de novas instruções

---

## 📊 Resultados Esperados

Este projeto demonstra:
- ✅ Vulnerabilidades de prompt injection em IaC
- ✅ Técnicas de sanitização e validação
- ✅ Evolução progressiva de segurança
- ✅ Importância de design defensivo em LLM

---

## 🎓 Contribuições Acadêmicas

Este trabalho contribui para:
- Pesquisa em segurança de LLM e IaC
- Boas práticas em design de prompts
- Estratégias de mitigação de riscos
- Frameworks para análise de código

---

## 📝 Versão
**v1.0** - Janeiro 2026

---

## 📧 Contato
**Autor**: Marcio M. Filho  
**MBA**: Arquitetura de Soluções em Cloud Computing  
**Universidade**: [Instituição]

## ENTREGÁVEL

Seguem os artefatos gerados para documentação final do projeto (entregável solicitado):

- `prompts/v1-baseline.md` — Versão baseline (V1). Raciocínio: fornecer um prompt funcional e direto que realiza a análise de IaC sem proteções; serve como linha de base para demonstrar riscos de prompt injection e identificar limitações iniciais.
- `prompts/v2-structured.md` — Versão estruturada (V2). Raciocínio: introduzir delimitadores de entrada, validações simples e detecção de padrões maliciosos para mitigar ataques comuns, mantendo formato de saída rígido.
- `prompts/v3-schema.md` — Versão schema (V3). Raciocínio: aplicar múltiplas camadas de validação (formato, anomalia, intenção), sanitização agressiva e regras anti-injection não negociáveis; foco em segurança robusta e auditoria de incidentes.

Resultados das execuções dos prompts contra os exemplos de teste estão em `resultados/`.
- `resultados/README.md` — Resumo das execuções e links para os arquivos de evidência.
- `resultados/*.jpg` — Placeholders para screenshots de cada execução (substitua por imagens reais se desejar).

Nome usado neste entregável: **Marcio Moreira FIlho**


---

## 📄 Licença
Este projeto é fornecido para fins educacionais e de pesquisa.

