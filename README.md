# 📁 Projeto: Provisionamento de Usuários, Grupos e Permissões no Linux

## 📌 Descrição
Este projeto consiste em um **script Bash** desenvolvido para **automatizar a criação de diretórios, grupos de usuários, usuários e a configuração de permissões** em sistemas Linux.

O script simula um **ambiente corporativo**, separando usuários por setores (Administrativo, Vendas e Segurança), aplicando **controle de acesso baseado em grupos**, seguindo boas práticas de organização e segurança.

---

## 🛠️ Tecnologias Utilizadas
- Linux
- Bash Script
- Comandos Linux:
  - `mkdir`
  - `groupadd`
  - `useradd`
  - `chown`
  - `chmod`
  - `openssl`

---

## 📂 Estrutura Criada

### 🔹 Diretórios
- `/publico` → acesso liberado para todos os usuários
- `/adm` → acesso restrito ao grupo administrativo
- `/ven` → acesso restrito ao grupo de vendas
- `/sec` → acesso restrito ao grupo de segurança

---

### 🔹 Grupos Criados
- `GRP_ADM` — Administrativo
- `GRP_VEN` — Vendas
- `GRP_SEC` — Segurança

---

### 🔹 Usuários Criados
Os usuários são criados com:
- Diretório home automático (`-m`)
- Shell padrão `/bin/bash`
- Associação a um grupo específico
- Senha criptografada com `openssl`

**Administrativo**
- carlos
- maria
- joao

**Vendas**
- debora
- sebastiana
- roberto

**Segurança**
- josefina
- amanda
- rogerio
- amanda1

---

## 🔐 Permissões Aplicadas

| Diretório | Proprietário | Grupo    | Permissão |
|----------|--------------|----------|-----------|
| /adm     | root         | GRP_ADM  | 770       |
| /ven     | root         | GRP_VEN  | 770       |
| /sec     | root         | GRP_SEC  | 770       |
| /publico | root         | root     | 777       |

📌 Apenas usuários pertencentes ao grupo correto têm acesso aos respectivos diretórios.

---

## ▶️ Como Executar
> ⚠️ O script deve ser executado como **root** ou utilizando `sudo`.

```bash
chmod +x script.sh
sudo ./script.sh
