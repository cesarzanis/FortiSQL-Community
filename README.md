# FortiSQL Ops - Community Edition

[![Release](https://img.shields.io/github/v/release/cesarzanis/FortiSQL-Community?color=C9B07A&label=Versao)](https://github.com/cesarzanis/FortiSQL-Community/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?logo=windows)](https://github.com/cesarzanis/FortiSQL-Community)
[![Consultoria](https://img.shields.io/badge/Consultoria-Czanix-blue?color=C9B07A)](https://czanix.com/pt/dados-bi)

Solução para automação de rotinas de backup, verificação de integridade (CHECKDB) e otimização de performance para Microsoft SQL Server. Ele integra a solução de manutenção do Ola Hallengren com um motor de pós-processamento, compactação em 7z e sincronização em nuvem, tudo configurado por uma interface gráfica simples e moderna.

## Principais Recursos

### 1. Automação de Backup (FULL, DIFF e LOG)
* **Agendamento Visual**: Interface gráfica linha a linha para definir horários de backup com snapping automático a minutos válidos (:00, :15, :30, :45).
* **Backups Diferenciais (DIFF)**: Realização automatizada de backups diferenciais inteligentes com base na data do último backup de dados.
* **Backup de Transações (LOG)**: Rotina automatizada a cada 15 minutos para bancos em modelo de recuperação FULL ou BULK_LOGGED.
* **Proteção contra Duplicação**: Janela de segurança de 5 minutos para evitar backups concorrentes.

### 2. Otimização & Integridade
* **Otimização de Índices e Estatísticas**: Reorganização ou reconstrução de índices e atualização de estatísticas integrada no pós-backup (marcado na própria linha de horário).
* **Validação de Integridade (CHECKDB)**: Verificação automática de integridade física e lógica dos arquivos de banco de dados (DBCC CHECKDB) para detecção de corrupções, com suporte a Physical Only, No Index, TabLock e Extended Checks.
* **Suporte a Azure SQL**: Ignora automaticamente backups e checagens estruturais para bancos gerenciados nativamente na nuvem (Azure SQL).

### 3. Compactação e Sincronização em Nuvem (Cloud Sync)
* **Compactação**: Compressão automática dos backups em arquivos .7z de alta eficiência de espaço (usando ferramenta 7-Zip embarcada).
* **Sincronização Cloud**: Cópia automática dos arquivos para pastas locais sincronizadas com a nuvem (Google Drive, OneDrive, Dropbox, etc.).
* **Limpeza Inteligente (Retention)**: Políticas de retenção local e em nuvem independentes. Limpeza automatizada de arquivos antigos se o espaço em disco atingir níveis críticos (smart reclamation).

### 4. Relatórios e Alertas
* **Relatório de Saúde**: Geração de um relatório de saúde em formato HTML traduzido em linguagem comercial/negocial, facilitando o acompanhamento por gestores que não têm conhecimento técnico profundo.
* **Histórico de Operações**: Histórico detalhado de comandos SQL executados com indicação de duração real (tarefas rápidas formatadas como < 1s).
* **Alertas**: Envio de relatórios visuais HTML para e-mails configurados (SMTP/TLS) e alertas curtos via Telegram.

## Como Instalar

1. Vá na aba de [Releases](https://github.com/cesarzanis/FortiSQL-Community/releases/latest) deste repositório.
2. Baixe o instalador mais recente: `FortiSQL_Setup_v2.2.0.exe`.
3. Execute o instalador no servidor Windows e siga as etapas do assistente.
4. Configure as credenciais do SQL Server (Windows Auth ou SQL Auth), ajuste os diretórios e configure os alertas por Telegram ou E-mail.
5. Salve e aplique. O agente ficará rodando na bandeja do sistema monitorando as rotinas de forma autônoma.

## Requisitos do Sistema

* **SO**: Windows Server 2012 R2 ou superior / Windows 10 ou superior (64-bit).
* **Banco de Dados**: Microsoft SQL Server 2012 ou superior (todas as edições, incluindo SQL Server Express, Web, Standard e Enterprise).
* **Acesso**: Permissões administrativas para instalação do serviço e login do agente no SQL Server com acesso de leitura/gravação aos bancos de dados a serem processados.

## Créditos e Honestidade Técnica

Por questão de honestidade intelectual e transparência técnica, com o objetivo de manter o projeto 100% correto com a comunidade, o motor de backup, integridade e otimização de índices do FortiSQL utiliza as rotinas de **Ola Hallengren** (disponíveis em [olahallengren.com](https://olahallengren.com)).

Consideramos as rotinas desenvolvidas por Ola como as melhores do mundo para a manutenção de SQL Server. Em vez de criar scripts novos e menos validados, o FortiSQL orquestra essa engenharia consolidada em uma interface gráfica simples, acrescentando agendamento visual, compactação em 7z, sincronização em nuvem e alertas por e-mail e Telegram.

## Licença & Suporte

Este projeto é disponibilizado sob o modelo Freemium pela Czanix Engineering. A edição Community é gratuita para uso pessoal ou avaliação.

Para suporte oficial, auditorias de banco de dados ou consultoria de infraestrutura SQL Server, acesse o site:
[Czanix Engineering - Consultoria de Banco de Dados](https://czanix.com/pt/dados-bi)
