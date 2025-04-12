#### **Descrição do Desafio**
Este projeto tem como objetivo criar um esquema conceitual do zero, utilizando o modelo Entidade-Relacionamento Estendido (EER) para atender às necessidades de controle e gerenciamento de ordens de serviço em uma oficina mecânica. O esquema deve capturar todas as entidades, relacionamentos e atributos descritos na narrativa fornecida, com complementos baseados na compreensão do contexto.

#### **Objetivo**
Desenvolver um modelo conceitual que inclua:
1. **Clientes** e seus veículos levados à oficina.
2. **Ordens de Serviço (OS)**, representando os serviços realizados e seus valores.
3. **Equipes de Mecânicos** e a atribuição de veículos a essas equipes.
4. **Tabela de referência de mão de obra** e valores de peças para cálculo da OS.

---

### **Modelo Conceitual**

1. **Cliente**:
   - Atributos:
     - ID do cliente (chave primária)
     - Nome
     - CPF
     - Contato (telefone, e-mail)
   - Relacionamento:
     - Cada cliente pode ter **múltiplos veículos** (1:N).

2. **Veículo**:
   - Atributos:
     - ID do veículo (chave primária)
     - Placa
     - Modelo
     - Ano
     - Tipo (ex.: Carro, Moto)
   - Relacionamento:
     - Cada veículo pertence a um cliente (1:1).
     - Cada veículo é atribuído a uma equipe de mecânicos (1:N).

3. **Equipe de Mecânicos**:
   - Atributos:
     - ID da equipe (chave primária)
     - Nome da equipe
   - Relacionamento:
     - Cada equipe é composta por vários mecânicos (1:N).
     - Cada equipe é responsável por veículos e ordens de serviço (N:M).

4. **Mecânico**:
   - Atributos:
     - Código do mecânico (chave primária)
     - Nome
     - Endereço
     - Especialidade (ex.: elétrica, motor, etc.)
   - Relacionamento:
     - Pertence a uma equipe (N:M).

5. **Ordem de Serviço (OS)**:
   - Atributos:
     - Número da OS (chave primária)
     - Data de emissão
     - Data de entrega
     - Status (ex.: "Aguardando autorização", "Em execução", "Finalizado")
     - Valor total
   - Relacionamento:
     - Cada OS está vinculada a um veículo (1:1).
     - Cada OS é preenchida e executada por uma equipe de mecânicos (1:N).
     - Serviços e peças contribuem para o cálculo do valor total da OS (N:M).

6. **Serviço**:
   - Atributos:
     - ID do serviço (chave primária)
     - Descrição
     - Valor da mão de obra (baseado na tabela de referência)
   - Relacionamento:
     - Associado a múltiplas OS (N:M).

7. **Peça**:
   - Atributos:
     - ID da peça (chave primária)
     - Descrição
     - Valor unitário
   - Relacionamento:
     - Associada a múltiplas OS (N:M).

