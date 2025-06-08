# 📄 Exemplo de Elaboração de PoC — API de Recomendação de Produtos

## 1. 🧭 Visão Geral

| Item | Descrição |
|------|-----------|
| **Nome da PoC** | RecoAPI |
| **Objetivo da PoC** | Validar a viabilidade técnica de uma API de recomendação de produtos em tempo real com base no histórico de navegação e perfil de cliente |
| **Stakeholders** | Produto (João), Engenharia (Ana), Dados (Carlos), UX (Bruna) |
| **Data de Início** | 10/06/2025 |
| **Data Prevista para Conclusão** | 17/06/2025 |

---

## 2. 🎯 Objetivos e Resultados Esperados

- **Hipóteses que serão validadas**:
  - É possível retornar recomendações personalizadas com latência < 200ms
  - A acurácia da recomendação é satisfatória (> 75% dos usuários clicam nos produtos sugeridos)

- **Resultados esperados**:
  - API REST funcionando com recomendação baseada em histórico + perfil
  - Simulação de carga com 500 RPS (requests per second)
  - Apresentação visual de produtos recomendados

---

## 3. 🔍 Escopo da PoC

| Item | Está Incluído? | Detalhes |
|------|----------------|----------|
| Integração com sistemas legados | ❌ | Apenas dados simulados |
| Banco de Dados real | ✅ | Redis (cache) e PostgreSQL |
| Autenticação de usuários | ❌ | API pública simulada |
| UI funcional | ✅ | Frontend com React para simulação |
| Dados reais ou simulados | Simulados | Histórico de navegação e perfis gerados artificialmente |

---

## 4. 🧱 Arquitetura da Solução (High Level)

- API REST desenvolvida em Python (FastAPI)
- Algoritmo de recomendação: matriz de similaridade item-item com fallback por categoria
- Cache com Redis para melhorar latência
- Frontend simples em React para visualização
- Testes de carga com Locust

---

## 5. 🛠️ Plano de Execução

| Fase | Atividade | Responsável | Data Início | Data Fim | Observações |
|------|-----------|-------------|-------------|----------|-------------|
| Planejamento | Gerar dataset simulado | Carlos | 10/06 | 11/06 | |
| Execução | Desenvolver API REST | Ana | 11/06 | 13/06 | |
| Execução | Criar frontend de simulação | Bruna | 12/06 | 13/06 | |
| Testes | Rodar testes de carga | Ana | 14/06 | 15/06 | |
| Validação | Testar com usuários internos | João | 15/06 | 16/06 | |
| Documentação | Relatório e entrega | Ana | 17/06 | 17/06 | |

---

## 6. 🧪 Critérios de Sucesso

| Critério | Métrica | Valor Esperado | Forma de Validação |
|----------|---------|----------------|---------------------|
| Performance | Tempo de resposta da API | < 200ms | Teste com Locust |
| Efetividade | Taxa de cliques nos produtos sugeridos | ≥ 75% | Simulação com usuários internos |
| Estabilidade | Uptime durante carga | ≥ 99% | Monitoramento |
| Simplicidade de integração | Documentação OpenAPI disponível | 100% | Swagger UI acessível |

---

## 7. 🚫 Riscos e Restrições

- **Riscos Técnicos**: Algoritmo pode não atingir taxa mínima de clique
- **Dependências externas**: Nenhuma (dados simulados)
- **Time disponível e capacidades**: Engenheira backend em outros projetos
- **Outras limitações**: Sem autenticação nem coleta de dados reais nesta fase

---

## 8. 📋 Checklist Final da PoC

| Item | Status |
|------|--------|
| Protótipo implementado | ✅ |
| Documentação técnica gerada | ✅ |
| Evidências de teste | ✅ |
| Reunião de encerramento realizada | ✅ |
| Avaliação com stakeholders | ✅ |

---

## 9. 📁 Entregáveis

- Repositório GitHub: `github.com/org/recoapi-poc`
- Documento técnico: `docs/recoapi-poc-report.pdf`
- Apresentação: `slides/recoapi-poc-pitch.pdf`
- Logs e testes de carga: `results/locust/`
- Aprendizados: `docs/retrospective.md`

---

## 10. 📝 Conclusões e Recomendações

- **Foi comprovada a viabilidade?** Sim
- **Sugestões para evolução**: Incluir dados reais, adicionar autenticação e ranking híbrido
- **Feedback dos stakeholders**: Muito positivo. Interface clara, resultados rápidos
- **Decisão final**: Aprovado para evolução em MVP
