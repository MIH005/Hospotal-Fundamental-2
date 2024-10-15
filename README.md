# Hospotal-Fundamental-2
Este diagrama apresenta um modelo de banco de dados voltado para a gestão hospitalar. Ele abrange diversas entidades, seus atributos e os relacionamentos entre elas. Abaixo está uma descrição detalhada de cada parte do diagrama:

### Entidades e seus Atributos:

1. **Médico**
   - Atributos: `Num_CRM`, `Nome_Med`, `Email_Med`, `Endereço_Med`, `Telefone_Med`, `Data_nasc_Med`
   - Relacionamentos:
     - Um médico pode ser generalista, especialista ou residente.
     - Relacionamento com a entidade **Internação** (um médico pode atender várias internações).

2. **Enfermeiro**
   - Atributos: `Num_COREN`, `CPF`, `Nome`, `COD_Enfermeiro`
   - Relacionamento com a **Internação** (enfermeiros podem ser responsáveis por internações).

3. **Pacientes**
   - Atributos: `CPF_Paci`, `Nome_Paci`, `Endereço_Paci`, `Telefone_Paci`, `Email_Paci`, `Data_nasc_Paci`, `Cod_Convenio`
   - Relacionamento com:
     - **Internação** (um paciente pode ficar em um quarto durante a internação).
     - **Convênio** (paciente pode ter um convênio).
     - **Receita** (paciente pode receber receitas após consultas).

4. **Internação**
   - Atributos: `Cod_Internação`, `CPF_Paci`, `Num_CRM`, `Data_Entrada`, `Data_Alta`, `Data_prev_Alta`, `Procedimento`
   - Relacionamento com:
     - **Médico** (um médico é responsável por internações).
     - **Enfermeiro** (um enfermeiro também pode ser responsável pela internação).
     - **Quarto** (internações ocupam quartos).

5. **Consulta**
   - Atributos: `Cod_Consulta`, `Data`, `Horario`, `Num_Carteira`, `Cod_Especialidade`, `Num_CRM`, `CPF_Paci`
   - Relacionamento com:
     - **Convênio** (cobre as consultas).
     - **Médico** (o médico realiza consultas).
     - **Receita** (consultas geram receitas).

6. **Receita**
   - Atributos: `Cod_Receita`, `Cod_Consulta`, `Instruções`, `Quantidade`
   - Relacionamento:
     - Receitas estão ligadas a consultas e têm medicamentos associados.

7. **Convênio**
   - Atributos: `Cod_Convenio`, `Nome_Convenio`, `CNPJ`, `Tempo_Carência`, `Valor_Consulta`
   - Relacionamento com:
     - **Pacientes** (pacientes podem ter convênios).
     - **Consultas** (convênios cobrem consultas).

8. **Quarto**
   - Atributos: `Cod_Quarto`, `Num_Quarto`, `Tipo`
   - Relacionamento com:
     - **Internação** (internações ocupam quartos).
     - **Tipo_Quarto** (define as características dos quartos).

9. **Tipo_Quarto**
   - Atributos: `Cod_Tipo_Quarto`, `Valor_Diario`, `Descrição`
   - Define o tipo de quarto disponível no hospital.

### Relacionamentos Importantes:
- **Médico** pode **atender** várias internações e consultas.
- **Enfermeiro** pode ser responsável por uma ou várias internações.
- **Pacientes** podem ser internados, realizar consultas e receber receitas.
- **Consultas** podem gerar receitas e ser cobertas por convênios.
- **Quartos** são ocupados durante internações e têm diferentes tipos, cada um com seu valor e descrição.
  
### Descrição Geral:
Este diagrama de banco de dados é projetado para gerenciar um sistema hospitalar. Ele abrange todas as entidades essenciais como médicos, enfermeiros, pacientes, internações, consultas e quartos, bem como os relacionamentos entre elas. Ele também lida com aspectos financeiros e administrativos, como convênios e receitas médicas, permitindo uma visão abrangente da gestão hospitalar.

![image](https://github.com/user-attachments/assets/c28ed743-cefb-45c1-830a-06c82890bfe4)

