# resumo-lab-dio-beneficios-da-nuvem-azure
Este repositório contém um resumo das lições aprendidas durante o desenvolvimento do lab da DIO 

## **1. O Que é SLA?**  
O SLA (Service Level Agreement) define o nível de serviço garantido por um provedor de nuvem, especificando métricas como disponibilidade, desempenho e suporte. No Azure, o SLA descreve a garantia de tempo de atividade de recursos como máquinas virtuais, bancos de dados e serviços de armazenamento.  

---

## **2. Categorias de SLA no Microsoft Azure**  

### **a. SLA de Disponibilidade**  
- **Máquinas Virtuais:**  
  - 99,9% para VMs de instância única usando discos Premium SSD.  
  - 99,95% para VMs com duas ou mais instâncias em um conjunto de disponibilidade.  
  - 99,99% para VMs em zonas de disponibilidade.

### **b. SLA de Armazenamento**  
- **Armazenamento Redundante:**  
  - **Locally Redundant Storage (LRS):** 99,9%  
  - **Zone-Redundant Storage (ZRS):** 99,99%  
  - **Geo-Redundant Storage (GRS):** 99,9% (leitura durante falhas: 99,99%)  
  - **Read-Access GRS (RA-GRS):** 99,99%  

### **c. SLA de Serviços Gerenciados**  
- Azure SQL Database: até 99,995%  
- Azure Kubernetes Service (AKS): 99,95%  

---

## **3. Cálculo de Tempo de Inatividade**  

### **Disponibilidade Prometida e Tempo de Inatividade Tolerado**  

| SLA (%)  | Tempo de Inatividade |  
|----------|------------------------|  
| 99%      | 7h 18m/mês ou 3d 15h/ano  |  
| 99,9%    | 43m 49s/mês ou 8h 45m/ano |  
| 99,95%   | 21m 54s/mês ou 4h 23m/ano |  
| 99,99%   | 4m 23s/mês ou 52m/ano     |  
| 99,999%  | 26s/mês ou 5m 15s/ano     |  

**Macete:** Quanto mais “noves” no SLA, menor é o tempo de indisponibilidade tolerado. Ex.: 99,9% (3 noves) é menos confiável que 99,99% (4 noves).  

---

## **4. Importância de Escolher o SLA Correto**  
Selecionar o SLA certo depende da criticidade do seu serviço:  
- **Aplicações de Missão Crítica:** Requerem SLAs mais altos (99,99% ou mais).  
- **Serviços Não-Críticos:** Podem operar com SLAs mais baixos para reduzir custos.  

Combinar serviços e regiões para garantir maior disponibilidade e resiliência.

---

## **5. Opções de Disponibilidade no Azure**  

### **a. Conjuntos de Disponibilidade (Availability Sets)**  
- Garantem alta disponibilidade distribuindo VMs em domínios de falha e atualização.  
- SLA típico: 99,95%.  

### **b. Zonas de Disponibilidade (Availability Zones)**  
- Garantem redundância geográfica dentro de uma região.  
- SLA típico: 99,99%.  

### **c. Redundância de Armazenamento**  
- **LRS:** Armazena dados localmente. Menor SLA.  
- **ZRS:** Armazena dados em zonas diferentes da mesma região.  
- **GRS:** Cópia geograficamente distante para recuperação de desastres.  

---

## **6. Relação Entre Arquitetura e SLA**  
- **Arquitetura de Alta Disponibilidade:** Combine VMs em zonas de disponibilidade e armazenamento GRS para maximizar o SLA.  
- **Resiliência:** Use múltiplas regiões e balanceamento de carga global para failover automático.  

---

## **7. Custo Versus SLA**  
SLAs mais altos geralmente resultam em custos maiores devido à necessidade de infraestrutura redundante. Escolha um equilíbrio entre custo e disponibilidade com base nos requisitos do seu negócio.  

---

Ter um entendimento claro do SLA no Azure ajuda a planejar arquiteturas resilientes e escolher serviços que garantam o nível de disponibilidade necessário.

