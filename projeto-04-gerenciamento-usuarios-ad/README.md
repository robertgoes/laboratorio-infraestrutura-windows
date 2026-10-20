# Projeto 04 — Gerenciamento de Usuários no Active Directory

## Objetivo

Simular um chamado de Help Desk N1/N2 envolvendo a criação de uma conta de usuário no Active Directory, a associação a um grupo de segurança e a validação do acesso a um compartilhamento de rede.

## Ambiente

- Windows Server com Active Directory.
- Cliente Windows 10 integrado ao domínio `labad.local`.
- Controlador de domínio: `SRV-AD01`.
- Ferramenta administrativa: Usuários e Computadores do Active Directory.

## Aplicação

- Criação do usuário fictício `Carlos Oliveira`.
- Configuração do nome de logon `carlos.oliveira`.
- Criação da conta na OU `LABORATÓRIO`.
- Configuração inicial da senha e posterior alteração da senha no primeiro acesso.
- Associação do usuário ao grupo de segurança `GRP_FINANCEIRO`.
- Consulta das propriedades da conta e dos grupos associados.

## Validação funcional

- Confirmação da existência da conta `Carlos Oliveira` na OU `LABORATÓRIO`.
- Verificação da associação ao grupo `GRP_FINANCEIRO`.
- Autenticação no cliente Windows 10 com a conta `labad\carlos.oliveira`.
- Execução do comando `whoami`, confirmando a identidade da sessão.
- Acesso ao compartilhamento de rede `\\SRV-AD01\Publico` usando a sessão de Carlos.

## Resultado

A conta de usuário foi criada e associada ao grupo `GRP_FINANCEIRO`. A autenticação no cliente Windows 10 foi confirmada, e o usuário conseguiu abrir o compartilhamento `\\SRV-AD01\Publico`.

O acesso ao compartilhamento foi validado. Entretanto, não foi realizada uma verificação específica das permissões efetivas para confirmar que o acesso foi concedido exclusivamente por meio do grupo `GRP_FINANCEIRO`.

## Conhecimentos praticados

- Active Directory Domain Services (AD DS).
- Criação e gerenciamento de contas de usuários.
- Unidades Organizacionais (OU).
- Grupos de segurança.
- Autenticação no domínio.
- Compartilhamentos de rede.
- Validação de acesso.
- Diagnóstico e documentação de atividades de Help Desk N1/N2.

## Status

**Aplicação:** Concluída.

**Validação funcional:** Concluída para autenticação e abertura do compartilhamento; validação das permissões efetivas pendente.
