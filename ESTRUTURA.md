# Estrutura de Arquivos e Descrição

## Organização do Projeto

```
projetosk8s/
│
├── 📄 README.md                          # Visão geral do projeto
├── 📄 requirements.txt                   # Dependências Python
├── 📄 .gitignore                        # Arquivos ignorados no git
│
├── 📁 docs/                             # Documentação técnica completa
│   ├── 01_INTRODUCAO.md                # Contexto e problema
│   ├── 02_FUNDAMENTACAO_TEORICA.md     # Conceitos e teoria
│   ├── 03_METODOLOGIA.md               # Abordagem e design
│   ├── 04_IMPLEMENTACAO.md             # Detalhes técnicos
│   └── 05_CONCLUSOES.md                # Resultados e recomendações
│
├── 📁 prompts/                          # Versões de prompts
│   ├── v1_basico.md                    # V1: Baseline sem proteções
│   ├── v2_melhorado.md                 # V2: Proteções intermediárias
│   ├── v3_robusto.md                   # V3: Proteção completa
│   └── guidelines.md                   # Boas práticas para design
│
├── 📁 terraform_examples/               # Exemplos de código Terraform
│   ├── exemplo_seguro.tf               # ✅ Código com boas práticas
│   ├── exemplo_inseguro.tf             # ❌ Anti-patterns e vulnerabilidades
│   └── exemplo_melhorado.tf            # 🔧 Transformação de inseguro para seguro
│
├── 📁 pr_samples/                      # Amostras de Pull Requests
│   ├── pr_valido.json                  # ✅ PR legítimo e seguro
│   ├── pr_malicioso_injection.json     # 🚨 PR com tentativa de injection
│   └── pr_complexo.json                # 🔍 PR complexo com múltiplas mudanças
│
└── 📁 security_tests/                  # Testes de segurança
    ├── test_prompt_injection.py        # Suite de testes principais
    ├── test_security_bypass.py         # (Futura) Testes de bypass
    └── test_results.md                 # Resultados dos testes
```

## Descrição de Cada Arquivo

### 📄 Raiz

| Arquivo | Descrição |
|---------|-----------|
| `README.md` | Visão geral do projeto, estrutura e como começar |
| `requirements.txt` | Dependências Python para executar os testes |
| `.gitignore` | Arquivos que não devem ser commitados |

### 📁 `/docs` - Documentação Técnica

| Arquivo | Conteúdo | Tamanho |
|---------|----------|--------|
| `01_INTRODUCAO.md` | Contexto, problema, objetivos e escopo | ~3 páginas |
| `02_FUNDAMENTACAO_TEORICA.md` | IaC, LLMs, Prompt Injection, segurança | ~5 páginas |
| `03_METODOLOGIA.md` | Abordagem de pesquisa, design de testes | ~4 páginas |
| `04_IMPLEMENTACAO.md` | Arquitetura, componentes, fluxo, performance | ~3 páginas |
| `05_CONCLUSOES.md` | Resultados, recomendações, roadmap futuro | ~4 páginas |

**Total**: ~19 páginas de documentação técnica

### 📁 `/prompts` - Versões de Prompts

| Versão | Proteção | Taxa Detecção | Uso |
|--------|----------|---------------|-----|
| `v1_basico.md` | Nenhuma | 0% | Baseline/Educacional |
| `v2_melhorado.md` | Básica | 60% | Testes intermediários |
| `v3_robusto.md` | Completa | 95%+ | ⭐ **PRODUÇÃO** |
| `guidelines.md` | N/A | N/A | Boas práticas de design |

### 📁 `/terraform_examples` - Exemplos de Código

| Arquivo | Tipo | Proposito | Problemas |
|---------|------|----------|-----------|
| `exemplo_seguro.tf` | ✅ Bom | Demonstrar padrões seguros | 0 críticos |
| `exemplo_inseguro.tf` | ❌ Ruim | Demonstrar vulnerabilidades | 10+ críticos |
| `exemplo_melhorado.tf` | 🔧 Transformação | Mostrar como corrigir | Antes/Depois |

### 📁 `/pr_samples` - Amostras de PR

| Arquivo | Tipo | Ataque | Uso |
|---------|------|--------|-----|
| `pr_valido.json` | Legítimo | Nenhum | Teste positivo |
| `pr_malicioso_injection.json` | Malicioso | Injeção direta + role change | Teste de segurança |
| `pr_complexo.json` | Legítimo | Nenhum (mas complexo) | Teste de análise |

### 📁 `/security_tests` - Testes Automatizados

| Arquivo | Descrição | Casos Testados |
|---------|-----------|----------------|
| `test_prompt_injection.py` | Suite principal | 8 tipos de ataque |
| `test_security_bypass.py` | (Futuro) Testes adicionais | TBD |
| `test_results.md` | Resultados executados | Taxa de sucesso por versão |

## Como Usar Este Projeto

### Leitura Recomendada (Ordem)

1. **Primeiro**: [README.md](README.md) - Visão geral
2. **Depois**: [docs/01_INTRODUCAO.md](docs/01_INTRODUCAO.md) - Contexto
3. **Teórico**: [docs/02_FUNDAMENTACAO_TEORICA.md](docs/02_FUNDAMENTACAO_TEORICA.md) - Conceitos
4. **Método**: [docs/03_METODOLOGIA.md](docs/03_METODOLOGIA.md) - Approach
5. **Técnico**: [docs/04_IMPLEMENTACAO.md](docs/04_IMPLEMENTACAO.md) - Detalhes
6. **Prático**: [terraform_examples/](terraform_examples/) - Exemplos
7. **Resultados**: [docs/05_CONCLUSOES.md](docs/05_CONCLUSOES.md) - Conclusões

### Para Entender as Versões

```
prompts/guidelines.md          ← Princípios de segurança
    ↓
prompts/v1_basico.md          ← Versão sem proteções (baseline)
    ↓
prompts/v2_melhorado.md       ← Proteções intermediárias (60% detecção)
    ↓
prompts/v3_robusto.md         ← Proteção completa (95%+ detecção)
    ↓
security_tests/test_results.md ← Resultados dos testes
```

### Para Executar Testes

```bash
# Instalação
pip install -r requirements.txt

# Executar
cd security_tests/
python test_prompt_injection.py

# Resultados
cat test_results.txt
```

### Para Entender Vulnerabilidades

```
terraform_examples/exemplo_inseguro.tf
    ↓
Identificar 10 problemas críticos
    ↓
terraform_examples/exemplo_melhorado.tf
    ↓
Ver como corrigir cada um
    ↓
terraform_examples/exemplo_seguro.tf
    ↓
Padrão final para produção
```

## Estatísticas do Projeto

- **Documentação**: ~20 páginas
- **Código Terraform**: ~800 linhas (seguro + inseguro + melhorado)
- **Código Python**: ~400 linhas (testes)
- **Casos de Teste**: 8 tipos de ataque
- **Linhas Totais**: ~2.000+
- **Taxa de Cobertura**: 95%+ de ataques testados
- **Tempo Estimado Leitura**: 2-3 horas completas

## Materiais de Apoio

### Referências Acadêmicas
- OWASP Top 10 for LLM Applications
- Prompt Injection Research Papers
- Terraform Security Best Practices
- AWS Security Architecture

### Links Úteis
- [OWASP](https://owasp.org/)
- [AWS Security](https://aws.amazon.com/security/)
- [Terraform Docs](https://www.terraform.io/docs)
- [Prompt Engineering](https://platform.openai.com/docs/guides/prompt-engineering)

## Próximos Passos Sugeridos

Para aprofundamento:

1. **Implementar**: Deploy V3 em staging
2. **Monitorar**: Coletar métricas reais
3. **Melhorar**: Implementar feedback loop
4. **Escalar**: Versão V4 com ML
5. **Publicar**: Pesquisa em conferência

---

**Última atualização**: Janeiro 2026  
**Status**: ✅ Completo para Apresentação de MBA

