# Configuração de Servidor DNS no Windows Server 2016

Este documento descreve o processo de instalação e configuração de um servidor DNS no Windows Server 2016.

## Índice

- [Pré-requisitos](#pré-requisitos)
- [Instalação do Servidor DNS](#instalação-do-servidor-dns)
- [Configuração do Servidor DNS](#configuração-do-servidor-dns)
- [Adicionando Registros DNS](#adicionando-registros-dns)
- [Verificação da Configuração](#verificação-da-configuração)
- [Configuração de Clientes](#configuração-de-clientes)
- [Dicas Finais](#dicas-finais)

## Pré-requisitos

- Windows Server 2016 instalado.
- Acesso ao servidor com privilégios de administrador.

## Instalação do Servidor DNS

1. Abra o **Gerenciador do Servidor**.
2. Clique em **Adicionar funções e recursos**.
3. Na tela **Antes de começar**, clique em **Avançar**.
4. Selecione **Instalação baseada em funções ou recursos** e clique em **Avançar**.
5. Escolha o servidor onde deseja instalar o DNS e clique em **Avançar**.
6. Na lista de funções, marque **Servidor DNS** e clique em **Avançar**.
7. Siga as instruções na tela e clique em **Instalar**. Aguarde a instalação ser concluída.

## Configuração do Servidor DNS

1. No **Gerenciador do Servidor**, clique em **Ferramentas** e selecione **DNS**.
2. Clique com o botão direito em **Zonas de Pesquisa Direta** e selecione **Nova Zona**.
3. No Assistente de Nova Zona, clique em **Avançar**.
4. Selecione **Zona Primária** e clique em **Avançar**.
5. Insira o nome da zona (exemplo: `meudominio.local`) e clique em **Avançar**.
6. Escolha o tipo de atualização desejado e clique em **Avançar**, depois em **Concluir**.

## Adicionando Registros DNS

1. Clique com o botão direito na zona criada e selecione **Novo Registro Host (A ou AAAA)**.
2. Insira o nome do host e o endereço IP correspondente.
3. Clique em **Adicionar Registro**.
4. Repita o processo para adicionar outros registros, como CNAME, MX, etc.

## Verificação da Configuração

- Abra o **Prompt de Comando** e use o comando `nslookup` para verificar a resolução do DNS.
- Exemplo de comando: `nslookup meudominio.local`.

## Configuração de Clientes

- Para que os dispositivos clientes utilizem o servidor DNS:
  - Defina o endereço IP do servidor DNS nas configurações de rede dos dispositivos cliente.
  - Você também pode configurar o DHCP para distribuir o endereço do servidor DNS automaticamente.

## Dicas Finais

- Verifique as regras de firewall para permitir o tráfego DNS (porta 53).
- Mantenha o Windows Server atualizado para garantir segurança e funcionalidade.
