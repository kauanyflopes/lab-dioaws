# ☁️ AWS CloudFormation - Desafio DIO

## 📘 Sobre o Projeto
Este repositório foi desenvolvido como parte do **Desafio da Digital Innovation One (DIO)**, com o objetivo de aplicar, na prática, os conceitos aprendidos sobre **infraestrutura como código (IaC)** utilizando **AWS CloudFormation**.

A proposta consiste em criar uma infraestrutura automatizada na AWS, utilizando templates em formato **YAML/JSON**, para provisionar e gerenciar recursos de forma padronizada e repetível.

---

## 🎯 Objetivos de Aprendizagem
- Aplicar os conceitos de **CloudFormation** na criação de recursos AWS;
- Compreender a estrutura de **templates, parâmetros, outputs e stacks**;
- Automatizar o provisionamento de infraestrutura;
- Documentar o processo técnico de forma clara e organizada;
- Publicar e versionar o projeto no **GitHub**.

---

## 🏗️ Arquitetura da Solução
O template principal (`main-template.yaml`) realiza o provisionamento automatizado de:
- Uma instância **EC2** com configuração básica;
- Um **Security Group** associado;
- Um **Bucket S3** para armazenamento de logs ou dados;
- (Opcional) Um **Elastic IP** ou **IAM Role**, conforme experimentação.

![Diagrama da Stack](./images/stack-created.png)

---

## ⚙️ Tecnologias Utilizadas
- **AWS CloudFormation**
- **Amazon EC2**
- **Amazon S3**
- **AWS IAM**
- **Git & GitHub**
- **YAML / JSON**

---

## 🧠 Estrutura do Template
Exemplo simplificado do template:

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Template para criar uma instância EC2 e um bucket S3

Resources:
  MyS3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: meu-bucket-cloudformation-${AWS::AccountId}

  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c02fb55956c7d316
      Tags:
        - Key: Name
          Value: InstanceCloudFormation
