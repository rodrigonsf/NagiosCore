# Instruções para agentes

## Objetivo do projeto

Este repositório automatiza a instalação e a configuração inicial do
Nagios Core 4.4.6 no CentOS 7.

O projeto é uma automação independente. Não implemente ou altere
o código-fonte do Nagios Core dentro deste repositório.

## Escopo

- Alterações devem manter compatibilidade com CentOS 7.
- Não adicione suporte a outras distribuições sem atualizar
  a documentação e testar o comportamento.
- Não altere a versão do Nagios Core sem atualizar README,
  documentação e validações.
- Não introduza credenciais reais, endereços IP reais, senhas
  ou dados privados em exemplos, templates ou testes.

## Estrutura esperada

- `nagios_automatizado.sh`: script principal de instalação.
- `docs/`: documentação de instalação, validação e solução de problemas.
- `LICENSE`: termos de uso e redistribuição.
- `SECURITY.md`: política de segurança.

## Regras de alteração

- Explique quais pacotes, arquivos, serviços ou regras serão alterados.
- Mantenha comandos idempotentes quando possível.
- Evite comandos destrutivos sem verificação prévia.
- Documente qualquer mudança que afete portas, firewall, SELinux,
  usuários, permissões ou serviços do sistema.
- Atualize o README e os documentos em `docs/` quando alterar
  o comportamento do instalador.

## Validação

Antes de sugerir alterações, verifique:

- Sintaxe do shell script.
- Compatibilidade com CentOS 7.
- Ausência de credenciais ou dados sensíveis.
- Clareza das mensagens de erro.
- Documentação atualizada.
- Comportamento em uma nova execução, quando aplicável.

## Segurança

- Não execute o instalador automaticamente em produção.
- Use ambientes isolados para testes de instalação.
- Não faça download de binários de fontes não verificadas.
- Não desabilite controles de segurança sem justificativa,
  documentação e aviso explícito ao usuário.
