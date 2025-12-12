# Gestão de Clientes - Conteúdo para Formandos


## PARTE 1: Porque é que a Estrutura de Clientes Importa?

### Cenário Real: Empresa de Vendas Online

Suponha que gere uma loja online com centenas de clientes.

**Sem uma boa estrutura:**
- Dados misturados em folhas de cálculo
- Nomes incompletos, endereços misturados, múltiplos emails
- Impossível filtrar clientes de uma cidade
- Duplicados (cliente João Silva aparece 3 vezes com dados ligeiramente diferentes)
- Encomendas perdidas, relatórios errados
- Crescimento impossível

**Com uma boa estrutura:**
- Cada cliente num registo único
- Dados organizados em campos específicos
- Filtrar por cidade: 1 clique
- Sem duplicados: chave primária garante ID único
- Encomendas ligadas a cliente específico
- Relatórios automáticos, crescimento escalável

**Conclusão:** Uma boa estrutura = Negócio escalável

---

## PARTE 2: Campos Essenciais de uma Tabela de Clientes

### O que é um "Campo Essencial"?

Um campo que **toda a** empresa precisa para gerir clientes profissionalmente.

### Lista Completa de Campos

#### **Grupo 1: Identificação (CRÍTICO)**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| **IDCliente** | NÚMERO | SIM | Chave Primária - identificador único (1, 2, 3...) |
| **NomeCliente** | TEXTO | SIM | Nome completo do cliente (João Silva) |
| **NIF** | TEXTO | NÃO | Número de Identificação Fiscal (123456789) |
| **Tipo** | TEXTO | SIM | Pessoa Singular ou Empresa |

**Porquê?**
- IDCliente garante que não há duplicados
- NomeCliente é informação básica
- NIF é importante para faturação
- Tipo diferencia pessoa singular de empresa

**Exemplo:**
```
IDCliente: 1
NomeCliente: João Silva
NIF: 123456789
Tipo: Pessoa Singular
```

---

#### **Grupo 2: Contacto Principal (CRÍTICO)**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| **EmailPrincipal** | TEXTO | SIM | Email principal (joao@email.com) |
| **TelefonePrincipal** | TEXTO | SIM | Telefone principal (912345678) |
| **EmailSecundário** | TEXTO | NÃO | Email alternativo |
| **TelefoneSecundário** | TEXTO | NÃO | Telefone alternativo |

**Porquê?**
- Email é contacto essencial (confirmação encomendas, newsletters)
- Telefone para contacto urgente
- Secundários para fallback se primeiro não funcionar

**Exemplo:**
```
EmailPrincipal: joao@email.com
TelefonePrincipal: 912345678
EmailSecundário: joao.silva@empresa.pt
TelefoneSecundário: 213456789
```

---

#### **Grupo 3: Morada (SEPARADA EM CAMPOS)**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| **Rua** | TEXTO | NÃO | Nome da rua e número (Rua Paz 123) |
| **CódigoPostal** | TEXTO | NÃO | Código postal (4000-001) |
| **Cidade** | TEXTO | NÃO | Cidade (Porto) |
| **País** | TEXTO | NÃO | País (Portugal) |

**Porquê? (CRUCIAL - Normalização)**
- Separado permite filtrar por cidade: "Cidade = Porto"
- Sem separar: endereço único impossibilita queries
- Com separado: gera relatórios por região automaticamente
- Com separado: ordena por código postal para envios

**ERRADO:**
```
Morada: "Rua Paz 123, 4000-001, Porto, Portugal"
```

**CORRETO:**
```
Rua: Rua Paz 123
CódigoPostal: 4000-001
Cidade: Porto
País: Portugal
```

---

#### **Grupo 4: Dados de Empresa (Se Aplicável)**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| **NomeEmpresa** | TEXTO | NÃO | Empresa (Centro Clínico João Silva Lda) |
| **Cargo** | TEXTO | NÃO | Cargo na empresa (Diretor Comercial) |
| **Departamento** | TEXTO | NÃO | Departamento (Vendas, Marketing) |
| **WebsiteEmpresa** | TEXTO | NÃO | Website empresa (www.empresa.pt) |

**Porquê?**
- Informação contextual importante
- Permite segmentação por empresa
- Útil para marketing B2B

---

#### **Grupo 5: Dados Comportamentais (Relacionados a Compras)**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| **DataRegisto** | DATA | SIM | Quando se registou (15-01-2024) |
| **DataÚltimaCompra** | DATA | NÃO | Quando comprou pela última vez |
| **TotalCompras** | MOEDA | NÃO | Total gasto até agora (€2.500,00) |
| **NúmeroCompras** | NÚMERO | NÃO | Quantas vezes comprou (15 compras) |

**Porquê?**
- Identifica clientes novos vs antigos
- Detecta clientes inativos
- VIP (cliente com €10k gastos) = atendimento especial
- Permite análise de tendências

---

#### **Grupo 6: Estado e Preferências**

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| **ClienteAtivo** | SIM/NÃO | SIM | Está ativo? (Sim/Não) |
| **RecebeNewsletters** | SIM/NÃO | NÃO | Quer newsletters? (Sim/Não) |
| **FormaDePagamentoPreferida** | TEXTO | NÃO | Cartão, Transferência, MB Way |
| **Notas** | TEXTO | NÃO | Observações (Texto livre até 500 caracteres) |

**Porquê?**
- Ativo: não enviar emails a clientes cancelados
- Newsletters: Conformidade com o RGPD (consentimento)
- Forma pagamento: otimizar checkout
- Notas: registo de informações importantes

---

### Resumo: Tabela Completa de Clientes

```
┌─────────────────────────────────────────────────────────────────┐
│                    TABELA DE CLIENTES                           │
├──────────┬──────────────┬──────┬──────────────────────────────────┤
│ IDCliente│ NomeCliente  │ NIF  │ Tipo                │ ... mais   │
├──────────┼──────────────┼──────┼──────────────────────┼────────────┤
│    1     │ João Silva   │12345 │ Pessoa Singular     │ ...        │
│    2     │ Maria Costa  │67890 │ Pessoa Singular     │ ...        │
│    3     │ ABC Lda      │54321 │ Empresa             │ ...        │
└──────────┴──────────────┴──────┴─────────────────────┴────────────┘
```

**14 Campos Principais** (após este ponto, campos são customizados por negócio)

---

## PARTE 3: Tipos de Dados em Prática

### Como Escolher Tipo Correto?

Cada campo tem tipo específico. Escolher errado = Problema.

### Exemplos Reais:

#### Exemplo 1: IDCliente

**Campo:** IDCliente  
**Tipo Correto:** NÚMERO  
**Porquê?** Permite cálculos, ordenação, relações com outras tabelas

**Tipo Errado:** TEXTO  
**Problema:** Não funciona em cálculos, relações falham

---

#### Exemplo 2: DataCadastro

**Campo:** DataRegisto  
**Tipo Correto:** DATA  
**Porquê?** Permite cálculos de data ("Quantos dias este cliente está connosco?")

**Tipo Errado:** TEXTO ("15-01-2024" como texto)  
**Problema:** Impossível calcular dias passados, ordenação falha (ordena como texto alfabético)

---

#### Exemplo 3: TotalCompras

**Campo:** TotalCompras  
**Tipo Correto:** MOEDA  
**Porquê?** Moeda formata automaticamente (€2.500,00), permite cálculos financeiros

**Tipo Errado:** TEXTO ("2500 euros")  
**Problema:** Não consegue somar totais clientes, sem formatação

---

#### Exemplo 4: ClienteAtivo

**Campo:** ClienteAtivo  
**Tipo Correto:** SIM/NÃO  
**Porquê?** Booleano, rápido de filtrar, sem ambiguidade

**Tipo Errado:** TEXTO ("Ativo", "Inativo", "Cancelado")  
**Problema:** Muito uso, sem padronização, filtros confusos

---

## PARTE 4: Relacionamentos Práticos

### O Que é um Relacionamento?

Tabela de Clientes conectada a outras tabelas.

### Exemplo: Clientes e Encomendas

**Tabela Clientes:**
```
IDCliente | NomeCliente
1         | João Silva
2         | Maria Costa
```

**Tabela Encomendas:**
```
IDEncomenda | IDCliente | DataEncomenda | Valor
1           | 1         | 15-01-2024    | €150
2           | 1         | 20-01-2024    | €200
3           | 2         | 18-01-2024    | €300
```

**Como Funciona?**
- Encomenda #1 pertence a Cliente IDCliente=1 (João Silva)
- Encomenda #2 pertence a Cliente IDCliente=1 (João Silva)
- Encomenda #3 pertence a Cliente IDCliente=2 (Maria Costa)

**IDCliente na tabela Encomendas é "Chave Estrangeira"** - referencia tabela Clientes

**Vantagem:**
- Uma vez escrito "João Silva", reutiliza-se em múltiplas encomendas
- Sem duplicação
- Se mudar email de João, muda num sítio apenas

---

### Outro Exemplo: Clientes e Contactos

Às vezes um cliente tem múltiplos contactos (5 pessoas numa empresa).

**Tabela Clientes:**
```
IDCliente | NomeEmpresa
1         | ABC Lda
2         | XYZ SA
```

**Tabela Contactos:**
```
IDContacto | IDCliente | NomeContacto  | Email
1          | 1         | João Silva    | joao@abc.pt
2          | 1         | Maria Costa   | maria@abc.pt
3          | 1         | Pedro Oliveira| pedro@abc.pt
4          | 2         | Alice Johnson | alice@xyz.sa
```

**Vantagem:**
- Empresa ABC tem 3 contactos: João, Maria, Pedro
- Query: "Todos contactos de ABC Lda" = fácil
- Sem repetição de dados empresa

---

## PARTE 5: Boas Práticas de Nomeação

### Convenções de Nomeação em Clientes

Toda a empresa profissional segue um padrão.

### Padrão Recomendado: PascalCase + Descritor

| Bom | Mau | Razão |
|-----|-----|-------|
| IDCliente | ID | Descritivo, claro |
| NomeCliente | Nome | Especifica "Cliente", não "Empresa" |
| EmailPrincipal | Email | "Principal" diferencia de secundário |
| TelefonePrincipal | Telefone | "Principal" diferencia de secundário |
| NIF | NIF | Claro, abreviatura internacional |
| DataRegisto | Data | "Registo" diferencia de "DataCompra" |
| ClienteAtivo | Ativo | Especifica que é cliente, não algo do sistema |
| TotalCompras | Total | "Compras" especifica contexto |

### Regras:

1. ✓ Comece sempre com maiúscula: `NomeCliente`
2. ✓ Sem espaços: `EmailPrincipal` (não "Email Principal")
3. ✓ Sem caracteres especiais: `NIF` (não "NIF-numero")
4. ✓ Descritivo: `DataRegisto` (não "Data1")
5. ✓ Consistente com outras tabelas: Se `IDCliente`, também `IDEncomenda` (não "NumeroEncomenda")

---

## PARTE 6: Evitar Erros Comuns

### Erro 1: Dados Misturados num Campo

**ERRADO:**
```
NomeCompleto: "João Silva, joao@email.com, 912345678"
```

**CORRETO:**
```
NomeCliente: João Silva
EmailPrincipal: joao@email.com
TelefonePrincipal: 912345678
```

**Porquê?** Impossível filtrar por email misturado com nome

---

### Erro 2: Sem Separação de Morada

**ERRADO:**
```
Morada: "Rua Paz 123, 4000-001 Porto"
```

**CORRETO:**
```
Rua: Rua Paz 123
CódigoPostal: 4000-001
Cidade: Porto
```

**Porquê?** Precisa filtrar por cidade para envios regionais

---

### Erro 3: Sem Chave Primária

**ERRADO:**
```
Tabela Clientes sem IDCliente - múltiplas "João Silva" sem distinguir
```

**CORRETO:**
```
IDCliente | NomeCliente
1         | João Silva
2         | João Silva (diferente)
```

**Porquê?** Sem ID, impossível saber qual João é qual encomenda

---

### Erro 4: Tipo Errado para Campo

**ERRADO:**
```
TotalCompras: TEXTO "€1.500"
```

**CORRETO:**
```
TotalCompras: MOEDA 1500.00
```

**Porquê?** Tipo MOEDA formata automaticamente, permite cálculos

---

### Erro 5: Campo Obrigatório Incompleto

**ERRADO:**
```
EmailPrincipal: Deixado vazio
```

**CORRETO:**
```
EmailPrincipal: joao@email.com (sempre preenchido)
```

**Porquê?** Email é crítico para comunicar com cliente

---

## PARTE 7: Análises Possíveis com Boa Estrutura

Com tabela bem estruturada, consegue:

### Query 1: "Quantos clientes tenho em Lisboa?"
> "Contar todos os clientes onde a Cidade é igual a 'Lisboa'"
**Resultado:** 245 clientes em Lisboa

---

### Query 2: "Qual cliente gastou mais?"
> "Mostrar o Nome e Total de Compras, ordenado do maior valor para o menor"
**Resultado:** João Silva €50.000 | Maria Costa €30.000 | ...

---

### Query 3: "Quantos dias está este cliente connosco?"
> "Calcular o número de dias desde a Data de Registo até Hoje para cada cliente"
**Resultado:** João Silva: 365 dias | Maria Costa: 45 dias | ...

---

### Query 4: "Clientes que não compram há 6 meses"
> "Procurar clientes cuja Data da Última Compra foi há mais de 6 meses"
**Resultado:** 12 clientes inativos - alvo para reativação

---

### Query 5: "Total faturação por cidade"
> "Somar o Total de Compras agrupando os resultados por Cidade"
**Resultado:** 
- Porto: €120.000
- Lisboa: €95.000
- Covilhã: €35.000

---

## PARTE 8: Checklists - Antes de Criar Tabela Clientes

### Checklist de Design

- [ ] Tabela tem chave primária (IDCliente)?
- [ ] Campos têm nomes descritivos?
- [ ] Nomes seguem convenção (PascalCase)?
- [ ] Tipos de dados apropriados?
- [ ] Campos obrigatórios bem definidos?
- [ ] Morada separada em campos (Rua, Código, Cidade)?
- [ ] Nomes e emails não misturados?
- [ ] Relacionamento clientes-encomendas clara?
- [ ] Sem duplicação de dados?

### Checklist de Campos Obrigatórios

- [ ] IDCliente (NÚMERO, chave primária)
- [ ] NomeCliente (TEXTO)
- [ ] EmailPrincipal (TEXTO)
- [ ] TelefonePrincipal (TEXTO)
- [ ] DataRegisto (DATA)
- [ ] ClienteAtivo (SIM/NÃO)

### Checklist de Campos Recomendados

- [ ] NIF (TEXTO)
- [ ] Rua (TEXTO)
- [ ] CódigoPostal (TEXTO)
- [ ] Cidade (TEXTO)
- [ ] DataÚltimaCompra (DATA)
- [ ] TotalCompras (MOEDA)
- [ ] RecebeNewsletters (SIM/NÃO)

---

## PARTE 9: Glossário

| Termo | Definição |
|-------|-----------|
| **Chave Primária** | Campo que identifica unicamente cada cliente (IDCliente) |
| **Chave Estrangeira** | Campo que referencia outra tabela (IDCliente em Encomendas) |
| **Relacionamento** | Conexão entre duas tabelas (Clientes ↔ Encomendas) |
| **Normalização** | Organizar dados em campos separados para evitar redundância |
| **Registo** | Uma linha na tabela (um cliente) |
| **Campo** | Uma coluna (NomeCliente, EmailPrincipal) |
| **Tipo de Dado** | Categoria (TEXTO, NÚMERO, DATA, MOEDA, SIM/NÃO) |
| **Obrigatório** | Campo que DEVE ter sempre um valor |
| **Valor Nulo** | Campo deixado vazio (não recomendado para campos obrigatórios) |

---

## PARTE 10: Próximos Passos

Esta Sessão cobre estrutura de **Clientes**.

Próximas Sessões cobrem:
- **Sessão 4**: Gestão de Fornecedores (estrutura, campos específicos)
- **Sessão 5**: Qualidade e Limpeza (como corrigir dados errados)
- **Sessão 6**: Segurança e Privacidade (RGPD, proteção)

---

## Perguntas Frequentes

### P: Preciso de TODOS estes campos?
**R:** Não. Os 6 campos obrigatórios são mínimo. Adicione campos conforme o negócio precisa.

### P: Posso mudar nomes de campos depois de criar?
**R:** Sim, mas com cuidado - se houver dados, nomes mudados podem quebrar consultas.

### P: O que é melhor: TEXTO ou NÚMERO para NIF?
**R:** TEXTO. NIF é "identificador", não número para cálculos (ex: 123456789 ≠ 123456788).

### P: Como evito duplicatas de clientes?
**R:** Chave primária (IDCliente) garante que cada cliente é único. Ao criar um novo cliente, gera um novo ID automaticamente.

### P: Posso ter dois emails numa coluna?
**R:** Não - viola normalização. Crie campos separados (EmailPrincipal, EmailSecundário).

---
