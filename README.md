
# 🚀 Projeto AWS CloudFormation - Infraestrutura como Código (IaC)

## 📌 Descrição do Desafio
Este desafio de projeto tem como objetivo **implementar a primeira Stack com AWS CloudFormation**, aplicando os conceitos aprendidos sobre **Infraestrutura como Código (IaC)** e automatização de recursos em nuvem.  

Durante o laboratório, foram desenvolvidos templates em **YAML/JSON**, explorando boas práticas no provisionamento de instâncias EC2, configuração de segurança e versionamento da infraestrutura.  

O repositório contém minhas anotações, insights e evidências, funcionando como um material de apoio para estudos futuros e novas implementações.

---

## 🎯 Objetivos de Aprendizagem
- Aplicar na prática os conceitos de **Infraestrutura como Código (IaC)**.  
- Compreender a utilização do **AWS CloudFormation** para automação de infraestrutura.  
- Documentar o processo técnico de forma clara e estruturada.  
- Utilizar o **GitHub como ferramenta de versionamento** e compartilhamento de documentação técnica.  

---

## 📝 Anotações de Estudo

### 🔹 O que é AWS CloudFormation
- É o serviço de **orquestração de recursos** da AWS, permitindo a criação e gerenciamento de infraestrutura por meio de **templates declarativos** (YAML/JSON).  
- Com ele, é possível provisionar recursos como:  
  - Instâncias **EC2**  
  - Bancos de dados **RDS**  
  - Redes **VPC** e subnets  
  - Regras de **Security Groups**  
  - Balanceadores de carga (**ELB**)  

✅ Elimina configurações manuais repetitivas.  
✅ Permite versionamento, padronização e reuso da infraestrutura.  

---

### 🔹 Benefícios do AWS CloudFormation
- **Automação:** provisiona ambientes inteiros em minutos.  
- **Consistência e Padronização:** reduz falhas humanas e garante ambientes idênticos.  
- **Economia de Tempo e Custos:** modelos reutilizáveis aceleram novas implementações.  
- **Segurança:** aplicação de políticas e regras pré-definidas.  

---

### 🔹 Estrutura de um Template CloudFormation
Um template típico inclui:  
- **Parameters** → valores de entrada do usuário.  
- **Mappings** → mapeamento de variáveis.  
- **Conditions** → regras condicionais para criação de recursos.  
- **Resources** → os recursos da AWS que serão criados.  
- **Outputs** → valores de saída úteis para consultas posteriores.  

---

### 🔹 Diferença entre CloudFormation e Terraform
- **CloudFormation**  
  - Exclusivo da AWS.  
  - Integração nativa e total com o ecossistema AWS.  
  - Indicado para ambientes **100% AWS**.  

- **Terraform**  
  - Multi-cloud (AWS, Azure, GCP etc.).  
  - Mais flexível para cenários híbridos.  
  - Popular em times que lidam com múltiplos provedores.  

---

## 📷 Evidências do Desafio

<img width="1840" height="867" alt="pagina de criação" src="https://github.com/user-attachments/assets/46579c39-f35e-44bb-9175-6b4f0a141d0f" />

### Criação de Stack no CloudFormation
- Upload de template (JSON/YAML) via S3, arquivo local ou Git.  
- Interface permite acompanhar status da criação em tempo real.  

<img width="1863" height="856" alt="pagina de composer" src="https://github.com/user-attachments/assets/670a9246-2634-481c-b621-243bfa3f33b7" />

### Infrastructure Composer
- Ferramenta visual que possibilita **arrastar recursos** (EC2, RDS, DynamoDB, API Gateway etc.).  
- Gera automaticamente o template em YAML/JSON.  
- Ideal para quem está aprendendo a estruturar stacks complexas.  



---

## 📚 Insights e Aprendizados
- Compreendi como o **IaC (Infraestrutura como Código)** simplifica o provisionamento e manutenção de ambientes.  
- Experimentei na prática como **CloudFormation** garante consistência ao replicar ambientes inteiros.  
- O uso de **templates YAML/JSON** fortalece o versionamento e a reutilização da infraestrutura.  
- Notei a importância de documentar o processo: o README funciona como **manual e registro de aprendizado**.  
- Reforcei que, para projetos multi-cloud, o **Terraform** pode ser mais adequado; mas dentro da AWS, **CloudFormation é a solução ideal** pela integração nativa.  

---

## 🔹 Exemplo de Template CloudFormation (JSON)
```json
{
  "Parameters": {
    "DBName": {
      "Default": "MyDatabase",
      "Description": "Nome do banco de dados MySQL",
      "Type": "String",
      "MinLength": "1",
      "MaxLength": "64",
      "AllowedPattern": "[a-zA-Z][a-zA-Z0-9]*"
    }
  },
  "Resources": {
    "MyEC2Instance": {
      "Type": "AWS::EC2::Instance",
      "Properties": {
        "InstanceType": "t2.micro",
        "ImageId": "ami-0c55b159cbfafe1f0"
      }
    }
  },
  "Outputs": {
    "InstanceId": {
      "Description": "ID da instância criada",
      "Value": {
        "Ref": "MyEC2Instance"
      }
    }
  }
}

````

🛠️ Ferramentas e Tecnologias Utilizadas
AWS CloudFormation → provisionamento de recursos.

AWS CLI → interação com serviços AWS via terminal.

GitHub → versionamento e compartilhamento do projeto.

YAML/JSON → criação de templates declarativos.



✅ Conclusão
Este desafio permitiu compreender, na prática, como aplicar Infraestrutura
como Código (IaC) utilizando o AWS CloudFormation.

A experiência mostrou a importância da automação, padronização e 
versionamento de ambientes, reforçando a relevância de práticas modernas de DevOps e Cloud.

📌 Esse projeto será usado como referência futura para provisionamento de ambientes reais em nuvem.


