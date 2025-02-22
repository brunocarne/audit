# Playbook de Auditoria de Comandos

Este playbook Ansible implementa um sistema de auditoria de comandos para servidores Linux, registrando todas as ações executadas pelos usuários via SSH.

## Funcionalidades

- Registra comandos executados por usuários
- Armazena timestamp de execução
- Captura IP do cliente SSH
- Identifica usuário real (inclusive em caso de sudo)
- Centraliza logs no arquivo `/var/log/audit_ssh.log`

## Pré-requisitos

- Ansible instalado no host de controle
- Acesso SSH aos servidores de destino
- Permissões de sudo nos servidores

## O que o playbook faz

1. Verifica e instala o rsyslog se necessário
2. Configura o `/etc/profile` com funções de auditoria
3. Configura o rsyslog para centralizar os logs
4. Reinicia serviços quando necessário

## Como usar

1. Configure seu inventário Ansible com os hosts de destino
2. Execute o playbook:

```bash
ansible-playbook playbook_audit.yaml -i seu_inventario
```
