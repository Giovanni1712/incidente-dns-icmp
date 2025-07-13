# Relatório de Incidente de Segurança: Análise de Tráfego DNS e ICMP

## Visão Geral

Este projeto apresenta a análise de um problema de rede que impediu o acesso ao site **www.yummyrecipesforme.com**. O erro exibido foi:  
**"porta de destino inalcançável"**.

Meu objetivo foi investigar o que estava acontecendo usando uma ferramenta de captura de pacotes chamada **tcpdump** para entender o problema.

---

## Resumo do Problema

- O navegador tentou consultar o servidor DNS para descobrir o endereço IP do site.
- Essa consulta foi feita usando o protocolo **UDP** na **porta 53**, que é a porta usada para DNS.
- O servidor DNS respondeu com uma mensagem de erro usando o protocolo **ICMP** dizendo que a **porta 53 estava inacessível**.
- Isso significa que o serviço DNS no servidor não estava funcionando corretamente ou a porta estava bloqueada.
- Como o DNS não respondeu, o navegador não conseguiu acessar o site.

---

## Análise Detalhada

- O problema aconteceu às **13:24:32** (horário registrado no sistema).
- Vários usuários reclamaram que não conseguiam acessar o site.
- Para investigar, usei o **tcpdump** para capturar o tráfego de rede enquanto tentava acessar o site.
- Observei que as consultas DNS eram enviadas, mas o servidor retornava um erro informando que a porta do serviço DNS estava inacessível.
- Isso indicou que o servidor DNS estava **desligado, com serviço parado ou com a porta bloqueada por firewall**.

---

## Próximos Passos para Resolver o Problema

1. Verificar se o servidor DNS está ligado e funcionando corretamente.
2. Garantir que a porta **UDP 53** está liberada no firewall.
3. Reiniciar o serviço DNS, se necessário.
4. Monitorar o servidor para evitar novos problemas.

---

## O que Aprendi

Essa análise mostrou a importância do serviço DNS para que os sites funcionem. Também aprendi que, mesmo sendo iniciante, é possível usar ferramentas como o **tcpdump** para identificar problemas de rede.

> *Adaptar. Aprender. Persistir. Tudo pelo sonho.*
