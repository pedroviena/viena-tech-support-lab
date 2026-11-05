# 🏢 VienaTech Corporation - Laboratório Prático de Infraestrutura Corporativa

Bem-vindo ao repositório de documentação do meu laboratório prático de Suporte de TI N2 e Infraestrutura.
Este projeto consistiu no planejamento, implantação e administração do zero da infraestrutura tecnológica da "VienaTech", simulando um ambiente corporativo real com gestão de identidades (Active Directory), automação, monitoramento e resolução de incidentes.

## 🚀 Arquitetura e Engenharia do Ambiente
O laboratório foi desenhado com foco em eficiência, adotando um modelo de arquitetura enxuta e segura (Lean Architecture), com isolamento de redes e serviços segmentados:

* **Hypervisor e Redes:** Oracle VirtualBox com topologia em modo *Internal Network* para isolamento completo de tráfego e simulação de LAN segura.
* **Controlador de Domínio:** Windows Server 2019 (AD DS, DNS, DHCP).
* **Estação de Trabalho Corporativa:** Windows 10 (Ingressada no domínio com políticas GPO restritivas).
* **Serviços de Dados e Monitoramento:** Fedora Linux Host executando serviços de banco de dados (PostgreSQL) e monitoramento containerizado (Zabbix via Docker) para máxima performance.

## 📂 Organização das Disciplinas do Laboratório
A documentação do projeto está dividida por serviços implementados e operação diária:

1. **Infraestrutura e Redes:** Implantação de LAN virtual, roteamento e distribuição de IP.
2. **Active Directory:** Promoção do Controlador de Domínio, arquitetura de Unidades Organizacionais (OUs) e aplicação de Políticas de Segurança (GPO).
3. **Troubleshooting Avançado:** Análise de tráfego corporativo com Wireshark e diagnósticos via CLI (`ping`, `nslookup`, `netstat`).
4. **Administração Linux:** Gestão do serviço PostgreSQL via `systemctl`, leitura de logs (`journalctl`) e administração de permissões.
5. **Automação de TI:** Provisionamento em massa de contas no Active Directory utilizando scripts em PowerShell baseados em arquivos CSV.
6. **Service Desk:** Base de conhecimento com chamados técnicos resolvidos, documentados no padrão de atendimento corporativo.

## 🛠️ Exemplo de Ticket Documentado (Service Desk)

**Ticket #INC-001: Cliente não consegue ingressar máquina no Domínio**
- **Sintoma:** Ao tentar conectar o Windows 10 ao domínio corporativo `viena.local`, o sistema retorna falha de resolução de nome (DNS).
- **Investigação:** Verificado via linha de comando na máquina cliente que a requisição de DNS estava sendo enviada para o gateway incorreto.
- **Causa Raiz:** Ausência de escopo DHCP configurado no Servidor apontando para o IP autoritativo do Controlador de Domínio (10.10.10.10).
- **Solução:** Configuração e ativação do escopo DHCP no Windows Server. Máquina cliente teve seu adaptador de rede atualizado para obter o novo IP/DNS. Ingresso no domínio realizado e validado com sucesso.
- 🔗 *Para acessar a documentação completa dos incidentes, acesse a pasta `07-service-desk-tickets`.*

---
*Este projeto demonstra de forma prática minha capacidade de administrar ambientes mistos, foco em Troubleshooting eficiente e operação alinhada às melhores práticas de infraestrutura de TI.*