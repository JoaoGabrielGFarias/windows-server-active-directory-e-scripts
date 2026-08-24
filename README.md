# 🖥️ Windows Server — Scripts de Automação e Infraestrutura

Este repositório reúne **scripts e ferramentas desenvolvidos durante meus estudos e práticas com Windows Server**, com foco em automação, administração de redes e gerenciamento de infraestrutura.

Os códigos aqui presentes foram criados para facilitar tarefas do dia a dia de um administrador de sistemas, abrangendo desde a criação de usuários no Active Directory até a configuração de serviços essenciais como DNS e DHCP.

---

## 📌 O que você vai encontrar aqui

- 🛠️ **Automação com PowerShell**
- 🧑‍💻 **Gerenciamento de usuários e grupos no AD**
- 🌐 **Configuração de DNS e DHCP**
- 🧠 **Políticas de Grupo (GPO) aplicadas via script**
- 📁 **Compartilhamento de arquivos e permissões**
- 📦 **Infraestrutura como código (IaC) com scripts prontos**
- 🧪 **Exemplos práticos para ambientes de laboratório e produção**

---

## 🚀 Exemplo de script

```powershell
# Criar usuários no Active Directory a partir de um arquivo CSV
Import-Csv .\usuarios.csv | ForEach-Object {
    New-ADUser -Name $_.Nome -SamAccountName $_.Login -Enabled $true -AccountPassword (ConvertTo-SecureString $_.Senha -AsPlainText -Force)
}
