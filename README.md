# Laboratório de Infraestrutura Windows

## Objetivo

Implementar e validar um ambiente virtualizado com Windows Server e Windows 10, simulando uma infraestrutura corporativa para atividades de suporte técnico N1/N2.

## Ambiente

* **Virtualização:** Hyper-V
* **Servidor:** SRV-AD01
* **Cliente:** CLIENTE-W10
* **Domínio:** labad.local
* **Switch interno:** LAB-AD (Internal)
* **Switch externo:** Internet (External)

## Topologia

```text
                    Hyper-V
                       |
                 Switch LAB-AD
                192.168.50.0/24
                  /          \
                 /            \
        SRV-AD01                CLIENTE-W10
        192.168.50.10           192.168.50.101
        AD DS / DNS             Cliente do domínio
                 |
          Switch Internet
             (External)
          192.168.15.10
          Gateway: 192.168.15.1
```

*Nota: o acesso externo e o serviço DHCP ainda precisam de validação específica.*

## Validações realizadas

### 1. Inventário do Hyper-V

As máquinas virtuais SERVIDOR-AD e CLIENTE-W10 estavam em execução, ambas na geração 2.

### 2. Conectividade IP

**Comando:**

```powershell
ping 192.168.50.10
```

**Resultado:** 4 pacotes enviados, 4 recebidos e 0% de perda.

### 3. Resolução DNS

**Comando:**

```powershell
nslookup labad.local
```

**Resultado:** o nome foi resolvido para 192.168.50.10 e 192.168.15.10. A resposta será revisada para confirmar se ambos os registros são esperados.

### 4. Identificação da conta

**Comando:**

```powershell
whoami
```

**Resultado:** a sessão retornou uma conta do domínio LABAD.

### 5. Descoberta do controlador de domínio

**Comando:**

```powershell
nltest /dsgetdc:labad.local
```

**Resultado:** o Windows localizou SRV-AD01.labad.local em 192.168.50.10 e concluiu o comando com êxito.

## Competências demonstradas

* Inventário de máquinas virtuais no Hyper-V.
* Identificação de switches e adaptadores virtuais.
* Interpretação de endereçamento IPv4 e DNS.
* Testes de conectividade e resolução de nomes.
* Verificação da descoberta de controlador de domínio.
* Registro de evidências técnicas para troubleshooting.

## Próximas melhorias

* Validar a origem da configuração IP do cliente e o serviço DHCP.
* Revisar a configuração DNS das interfaces do servidor.
* Adicionar capturas de tela dos testes.
* Documentar um caso de troubleshooting com diagnóstico, correção e validação.

## Evidências do laboratório

### Switch virtual LAB-AD — Hyper-V

![Configuração do switch virtual LAB-AD](images/hyperv-switch-lab-ad.png)

