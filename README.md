# Nagios Core Installer — CentOS 7
Automated installation and configuration of Nagios Core 4.4.6
on CentOS 7.

Automação de instalação e configuração do Nagios Core 4.4.6
no CentOS 7. <br> <i>(It´s automatic ♪♫)</i>
<b>(<i>atcho tcho meri ♪♫</i>) ;-)</b>

## Status / Estado do projeto

Este projeto tem como alvo um ambiente legado: CentOS Linux 7.

O CentOS Linux 7 chegou ao fim de vida em 30 de junho de 2024
e não recebe mais atualizações oficiais. Considere este projeto
para estudo, referência e avaliação de ambientes legados, não
como recomendação para novas implantações em produção.

This project targets a legacy environment: CentOS Linux 7,
which reached end of life on June 30, 2024.

## Sobre o projeto

Este repositório contém um shell script para automatizar a
instalação e a configuração do Nagios Core.

É um projeto independente de automação. Não é o código-fonte
do Nagios Core nem um instalador oficial do produto.

### Ambiente-alvo

- Sistema operacional: CentOS 7.
- Versão do Nagios Core indicada pelo projeto: 4.4.6.
- Script principal: `nagios_automatizado.sh`.

O funcionamento em outras distribuições ou versões não é
declarado neste README.

## Antes de executar

- Leia o script completo.
- Verifique os arquivos, pacotes e serviços que ele modifica.
- Faça backup dos dados e configurações relevantes.
- Avalie primeiro em uma máquina virtual descartável.
- Execute apenas se compreender e aceitar as alterações.

A instalação requer privilégios administrativos.

## Instalação

### 1. Baixe o script

Substitua `URL_RAW_CONFIRMADA_DO_SCRIPT` pelo endereço válido
do arquivo neste repositório:

```bash
wget -O nagios_automatizado.sh "URL_RAW_CONFIRMADA_DO_SCRIPT"
```

### 2. Revise o conteúdo

Abra `nagios_automatizado.sh` em um editor de texto e leia
o conteúdo antes de prosseguir.

### 3. Execute

```bash
chmod 755 nagios_automatizado.sh
sudo ./nagios_automatizado.sh
```

Se você já estiver em uma sessão de root, execute sem `sudo`:

```bash
./nagios_automatizado.sh
```

### 4. Limpeza opcional

Após concluir a instalação, você pode remover a cópia local
do instalador:

```bash
rm nagios_automatizado.sh
```

Isso remove somente o arquivo do script, não desinstala o Nagios.

## Validação da instalação

Esta seção deve documentar:

- Como verificar se o serviço foi iniciado.
- Como validar a configuração do Nagios.
- Como acessar a interface web, quando aplicável.
- Onde consultar os logs em caso de erro.

## Limitações

- Projeto voltado ao CentOS 7.
- O sistema operacional está fora de suporte.
- Dependências e endereços de download podem precisar de ajustes.
- Revise o script antes de executá-lo em qualquer ambiente.

## English summary

This repository provides a shell script to automate Nagios Core
4.4.6 installation and configuration on CentOS 7.

Read the entire script before running it with administrative
privileges. Test it in a disposable environment first.

CentOS Linux 7 is end-of-life. This project should be evaluated
as legacy automation, not as a recommendation for new
production deployments.

## Aviso de responsabilidade / Disclaimer

O script é fornecido "como está", sem garantias de qualquer
natureza. Avalie sua adequação ao ambiente antes de executá-lo.

The script is provided "as is", without warranties of any kind.
Review it and assess its suitability before use.
