Documentação de Configuração de Ambiente Virtual: Ubuntu Server 24.04 LTS

📋 Visão Geral
Este documento detalha o processo de provisionamento e configuração de uma máquina virtual (VM) utilizando o Oracle VirtualBox para fins de estudo em Desenvolvimento Full Stack e Segurança da Informação. O objetivo foi estabelecer um servidor Linux funcional com conectividade de rede externa e armazenamento adequado.

🛠️ Especificações do Ambiente
Hypervisor: Oracle VirtualBox

Sistema Operacional Guest: Ubuntu Server 24.04.4 LTS

Arquitetura: x86_64 (amd64)

🔧 Etapas de Configuração
1. Provisionamento de Armazenamento (Storage)
Durante a fase inicial, foi identificado que o espaço em disco padrão ou configurado incorretamente impedia a instalação.

Ajuste: Criação de um Volume de Disco Virtual (VDI) de 26.33 GB.

Tipo de Alocação: Dinamicamente alocado (otimização de espaço no host).

Controladora: Vinculação do disco à Controladora SATA para garantir performance e compatibilidade com o instalador moderno.

2. Configuração de Rede (Networking)
Para permitir que o servidor fosse acessível por outros dispositivos na rede local e realizasse atualizações de pacotes:

Modo de Rede: Alterado de NAT para Placa em Modo Bridge (Bridge Adapter).

Interface: Vinculada ao adaptador de rede física (Wi-Fi/Ethernet) do host.

Resultado: Atribuição bem-sucedida de endereço IP via DHCP na sub-rede local.

3. Gerenciamento de Mídia
Configuração da Controladora IDE com a imagem ISO oficial do Ubuntu Server para o processo de boot e instalação (Live Installer).

🚀 Desafios Superados
Erro de "Block Probing": Resolvido através da readequação do tamanho do disco virtual, garantindo que o sistema tivesse o mínimo de 20GB necessários para as partições do SO.

Conectividade: Correção da interface de rede desabilitada nas configurações do hypervisor, permitindo a comunicação via protocolo IPv4.

📚 Aplicação Prática
Este servidor será utilizado como base para:

Laboratórios de ataques controlados (Cybersecurity).

Deploy de aplicações Node.js/Python (Full Stack).

Estudos de gerenciamento de servidores para o concurso do Banco do Brasil.
