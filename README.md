# 💻 Desafio | Configurando uma Instância de Banco de Dados na Azure
Repositório criado para o desafio de configuração de uma Instância de Banco de Dados na plataforma **Microsoft Azure**, proposto pela [Digital Innovation One (DIO)](https://www.dio.me/).

---
## 📚 Documentação do Processo

1. Acesse o portal da Azure: https://portal.azure.com.

2. Na página inicial, procure e selecione por Instâncias Gerenciadas do SQL.

3. Após selecionar, clique em `+ Criar`.

4. Agora é necessário colocar informações obrigatórias no **Básico**.

### ⚙ Básico

5. **Assinatura**

 - Selecione sua assinatura do Azure, Grupo de Recursos é algo opcional.

6. **Detalhes da Instância Gerenciada**

- Coloque o Nome e a Região da Instância que será criada

- Se ela pertencer a um pool de instâncias, selecione a opção sim

7. **Método de Autenticação** 
- Selecione a opção SQL e coloque um nome de usuário válido em Logon de administrador da Instância Gerenciada e uma senha válida.

8. Em Detalhes da instância gerenciada, selecione Configurar instância gerenciada na seção Computação + armazenamento para abrir a página `Computação + armazenamento`.

9. **Configurar instância gerenciada**

- Em Camada de Serviço, selecione Uso Geral (padrão). É ideal para a maioria das cargas de trabalho de produção.

- Em Geração de Hardware, use a Série Standard (Gen5) (opção padrão). Isso define limites de CPU e memória.

- Em vCores, defina a quantidade de vCores conforme a carga esperada.Valor padrão: 8 vCores.

- Em Armazenamento (em GB),especifique o tamanho do armazenamento com base nos dados esperados.

- Em Licença do SQL Server,selecione um modelo de licenciamento:
`Pagamento conforme o uso`/ `Benefício Híbrido do Azure (licença existente)`/ `Failover híbrido habilitado`/ `Redundância do Armazenamento de Backup`

- Escolha o tipo de redundância:
`Geográfica (padrão e recomendada)` / `Local` / `Zona geográfica`

- Clique em Aplicar para salvar as configurações. Você será redirecionado para a página de criação da instância.

10. Clique em `Próximo` para configurar a **Rede**.

### 🌎 Rede

11. **Rede virtual / sub-rede**
- Crie ou use uma rede virtual existente.	Se uma rede ou sub-rede não estiver disponível, ela deverá ser modificada para atender aos requisitos de rede antes de selecioná-la como um destino para a nova instância gerenciada de SQL.

12.  **Tipo de conexão**
- Escolha um tipo de conexão adequado.

13.  **Ponto de extremidade público**
- Selecione `Desabilitar`.

14. **Permitir o acesso de (se o Ponto de extremidade público estiver habilitado)**
- Selecione `Sem Acesso`. 

15. Defina as configurações de segurança selecionando `Avançar: Configurações de segurança`.

### 🔐 Segurança

16. Deixe as configurações na guia Segurança em seus valores padrão. Clique em `Avançar: configurações adicionais`.

### ➕ Configurações adicionais

17. Preencha as informações opcionais na guia Configurações adicionais. Se você omitir essas informações, o portal aplicará as configurações padrão.

18. **Ordenação**	
- Escolha a ordenação que você deseja usar para sua instância gerenciada de SQL.

19. **Fuso horário**
- Selecione o fuso horário observado pela instância gerenciada de SQL.	

20. **Replicação geográfica**	
- Selecione `Não`.	
- Habilite essa opção somente se você planeja usar a instância gerenciada de SQL como um grupo de failover secundário.

21. **Janela de manutenção**
- Escolha uma janela de manutenção adequada.
- Designe um agendamento para quando sua instância for mantida pelo serviço.

22. Agora configure as marcas do Azure selecionando `Avançar: Marcas` (recomendado).

### 📝 Marcações
23. Adicione marcas para organizar os recursos, facilitar a gestão e o controle de custos. Use, por exemplo, as marcas Proprietário (quem criou) e Ambiente (Produção, Desenvolvimento etc).

24. Na guia `Revisar + criar` , examine suas escolhas e selecione Criar para implantar sua instância gerenciada de SQL.

25. Depois que a implantação for concluída, navegue até o grupo de recursos para exibir sua instância gerenciada de SQL.


---
## 🔎 Observações

- Grupo de Recursos: Ajuda na organização e no gerenciamento dos recursos.

- Redundância: Geográfica é mais segura, mas pode ser mais cara.

- vCores e Armazenamento: Ajuste conforme a carga para evitar custos desnecessários.

- Licenciamento: Use o Benefício Híbrido se já tiver licença SQL Server.

- Rede Virtual: A sub-rede deve ser exclusiva para a instância.

- Ponto de extremidade público: Evite habilitar para reduzir riscos de segurança.

- Tags (Marcas): Facilita controle de custos e governança.

- Janela de Manutenção: Escolha horários de baixa demanda.

- Pós-implantação: Verifique conectividade, autenticação e monitoramento inicial.


---

## 🔍 Referências

- [📘 Microsoft Learn – Guia Rápido](https://learn.microsoft.com/pt-br/azure/azure-sql/managed-instance/instance-create-quickstart?view=azuresql&tabs=azure-portal)
- [🌐 Digital Innovation One (DIO)](https://www.dio.me/)
