### Projeto — GPO de Bloqueio por Inatividade

**Objetivo:** Configurar uma Política de Grupo (GPO) para definir o tempo limite da proteção de tela e exigir senha para retomar a sessão.

**Ambiente:** Windows Server com Active Directory e cliente Windows 10 integrado ao domínio `labad.local`.

**Aplicação:**

- Criação e vinculação da GPO `GPO_Lab_Bloqueio_Inatividade`.
- Habilitação da política de proteção de tela com senha.
- Configuração do tempo limite para 20 segundos.
- Atualização das políticas de grupo no cliente Windows 10.

**Validação funcional:**

- Verificação do resultado da política por meio do registro do Windows.
- Confirmação do valor de 20 segundos no registro de políticas.
- Teste de inatividade no cliente Windows 10.

**Conhecimentos praticados:** Active Directory, Group Policy Management, configuração de GPOs, registro do Windows e troubleshooting de políticas de usuário.

**Status da aplicação:** Configuração realizada.
