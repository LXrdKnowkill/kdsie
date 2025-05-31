# 🔥 DragonBurn - CS2 External Cheat 🔥

[![Build Status](https://github.com/bytecorum/dragonburn/actions/workflows/build-check.yml/badge.svg)](https://github.com/bytecorum/dragonburn/actions/workflows/build-check.yml)
[![Pull Requests](https://img.shields.io/github/issues-pr/bytecorum/dragonburn?color=0088ff)](https://github.com/bytecorum/dragonburn/pulls)
[![Issues](https://img.shields.io/github/issues/bytecorum/dragonburn?color=ff0000)](https://github.com/bytecorum/dragonburn/issues)

**Domine o campo de batalha com DragonBurn, uma base de cheat externo para Counter-Strike 2, construída com a precisão do C++ moderno e a elegância da interface gráfica ImGui. Desenvolvido com foco em performance, customização e uma arquitetura sólida para futuras expansões.**

Este projeto é um sucessor espiritual e uma evolução de bases de cheats externas para CS:GO, agora totalmente adaptado e otimizado para os desafios e nuances do CS2.

## 🌟 Funcionalidades de Elite

DragonBurn vem equipado com um arsenal de funcionalidades projetadas para oferecer vantagem tática, mantendo a fluidez e a resposta imediata.

* **🎯 Aimbot:**
    * Precisão cirúrgica com FOV (Field of View) customizável.
    * Suavização (Smoothing) para movimentos mais humanos.
    * Seleção de Bone (osso alvo).
    * Verificação de visibilidade e modo "somente visível".
    * Configurações por arma.
* **🔫 TriggerBot:**
    * Disparo automático ao mirar em um inimigo.
    * Delay customizável para simular reação humana.
    * Verificação de rajada (Burst check).
* **👁️ ESP (Extra Sensory Perception):**
    * **Player ESP:** Caixas (2D, 3D), Nomes, Vida, Armadura, Arma equipada, Distância.
    * **Skeleton ESP:** Visualização do esqueleto do jogador.
    * **Snaplines:** Linhas direcionadas aos inimigos.
    * **Item ESP:** Localização de armas e granadas no mapa.
    * **C4 Timer:** Cronômetro para a C4 plantada, com informações de tempo para defuse.
* **📡 Radar 2D:**
    * Exibe inimigos e aliados no radar customizável.
    * Níveis de zoom e transparência ajustáveis.
* **💨 RCS (Recoil Control System):**
    * Controle de recuo personalizável para manter a mira estável.
    * Ajuste de força horizontal e vertical.
* **📜 Lista de Espectadores:**
    * Identifica quem está te assistindo, para maior cautela.
* **⚙️ Miscelânea:**
    * **BunnyHop:** Salto contínuo automatizado.
    * **Auto Strafe:** Movimentação lateral otimizada durante saltos.
    * **FOV Changer:** Ajuste do campo de visão do jogo.
    * E outras utilidades para aprimorar a experiência.
* **🎨 Interface Gráfica (ImGui):**
    * Menu intuitivo e completo, renderizado com Dear ImGui.
    * Fácil customização de todas as funcionalidades em tempo real.
    * Design moderno e responsivo.
* **💾 Sistema de Configuração:**
    * Salve e carregue suas configurações preferidas.
    * Baseado em JSON para fácil edição e compartilhamento.

## 🛠️ Tecnologias Empregadas

Este projeto é construído sobre uma fundação sólida de C++ e bibliotecas de ponta:

* **Linguagem Principal:** C++20 (ou C++17, conforme `CMakeLists.txt`) – Aproveitando os recursos modernos para performance e clareza.
* **Interface Gráfica:** [Dear ImGui](https://github.com/ocornut/imgui) – Para uma UI flexível, poderosa e com ótima aparência.
* **Manipulação de JSON:** [nlohmann/json](https://github.com/nlohmann/json) – Para um sistema de configuração robusto e fácil de usar.
* **Sistema de Build:** CMake – Para compilação multiplataforma e gerenciamento de dependências simplificado.
* **Interação com o Sistema:** Windows API (para leitura de memória e manipulação de janelas).
* **Renderização:** DirectX 11 (para integração do ImGui com o jogo).


## 🛡️ Bypass e Segurança (A Arte da Evasão)

No desenvolvimento de cheats, a discrição é fundamental. DragonBurn é concebido com técnicas que visam minimizar a detecção, mas a guerra contra anti-cheats é um jogo de gato e rato constante.

* **Leitura de Memória Externa:** Operamos externamente ao processo do jogo, uma abordagem classicamente mais segura que a injeção interna, mas que ainda requer astúcia.
* **Chamadas de Sistema:** Atenção é dada à forma como interagimos com o sistema operacional e o processo alvo.
* **Assinaturas e Heurísticas:** O código é estruturado para evitar padrões óbvios que anti-cheats podem identificar.

**Nota do Desenvolvedor:** *Nenhum cheat é 100% indetectável para sempre. A eficácia de um bypass depende da sofisticação do anti-cheat e das técnicas empregadas. Para máxima resiliência, especialmente contra anti-cheats a nível de kernel, a integração com um **driver kernel customizado** para operações de leitura/escrita de memória e outras interações sensíveis é o próximo nível de blindagem. Este é um campo onde a verdadeira expertise em C++ e sistemas internos brilha, permitindo operações furtivas e controle granular, muito além do que o usermode pode oferecer com segurança a longo prazo.*

## 🚀 Potencializando com Drivers Kernel (O Ápice da Furtividade)

Para os que buscam o estado da arte em termos de bypass e robustez, a comunicação com um **driver kernel (Kernel-Mode Driver - KMD)** é o caminho.

* **Acesso Privilegiado:** Drivers operam no Ring 0, permitindo acesso direto ao hardware e à memória do sistema de forma que é significativamente mais difícil de detectar ou bloquear por anti-cheats em usermode.
* **Manipulação de Memória Segura:** Operações como `ReadProcessMemory` e `WriteProcessMemory` podem ser implementadas no kernel, mascarando a origem das chamadas e bypassando hooks comuns em usermode.
* **Proteção do Cheat:** O próprio cheat pode ser melhor protegido contra detecção e análise quando certas funcionalidades críticas são delegadas a um componente kernel.

A criação e utilização de drivers kernel é uma disciplina avançada, exigindo profundo conhecimento de programação de sistemas Windows, arquitetura de CPU e mecanismos de anti-cheat. DragonBurn, em sua forma atual, é uma base usermode, mas sua arquitetura modular permite a integração futura com um backend KMD para quem desejar trilhar esse caminho de maestria.

## 🤝 Contribuições

Contribuições são bem-vindas! Se você tem ideias para novas funcionalidades, otimizações, ou correções de bugs:

1.  Faça um Fork do projeto.
2.  Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`).
3.  Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`).
4.  Push para a branch (`git push origin feature/AmazingFeature`).
5.  Abra um Pull Request.

## 📜 Aviso Legal

* Este software é fornecido **APENAS PARA FINS EDUCACIONAIS**.
* O uso deste software em servidores de jogos online pode resultar em **BANIMENTO** da sua conta.
* Os desenvolvedores não se responsabilizam por qualquer uso indevido deste software ou por quaisquer consequências negativas decorrentes de seu uso.
* **USE POR SUA CONTA E RISCO.**

---

*Feito com paixão por C++ e pela arte da engenharia reversa.*
*Queime seus oponentes. Com responsabilidade.*
