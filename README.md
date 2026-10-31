# Guia de Manutenção e Substituição de Painel LCD: LG Flatron M1721A / M1921A

Este repositório é um guia prático dedicado à manutenção corretiva, preventiva e substituição do painel LCD dos monitores-TV **LG Flatron M1721A** (17 polegadas) e **M1921A** (19 polegadas).

---

## 🚀 Os Queridinhos da Retrocomputação: Vantagens e Características

Os modelos M1721A e M1921A ganharam status de "culto" no ecossistema retro brasileiro devido a uma característica técnica crucial: a **capacidade nativa de aceitar varredura horizontal de 15 kHz** através da porta VGA (além de possuírem entradas físicas de Vídeo Composto, S-Video e Áudio RCA). 

### Vantagens Únicas:
* **Frequência de 15 kHz Nativa:** Permite ligar computadores clássicos — como o MSX, Amiga, Commodore, e Apple II — ou consoles antigos direto na porta VGA sem a necessidade de *upscalers* ou conversores caros.
* **Proporção de Tela 5:4 (Resolução 1280x1024):** Preserva o aspecto visual ideal para sistemas antigos se comparado aos monitores *widescreen* modernos.
* **Versatilidade:** Atua como Monitor e TV ao mesmo tempo, facilitando a bancada de testes de qualquer colecionador.

---

## ⚠️ O Calcanhar de Aquiles: Problemas Crônicos

Apesar de brilhantes, o peso da idade trouxe duas grandes desvantagens críticas que este projeto visa solucionar:

1. **Degradação do Painel LCD:** O defeito mais visível é o **descolamento e vinco da camada reflexiva/polarizadora**. Isso gera um aspecto visual "esbranquiçado", formação de "bolhas" permanentes na tela e o surgimento precoce de *dead-pixels*. **O escopo deste repositório foca exclusivamente na documentação para a substituição completa do painel danificado por telas compatíveis retiradas de outros modelos (monitores doadores), e não no processo de troca manual da película polarizadora.**
2. **Os "Capacitores Suicidas" da Fonte:** Conforme alertado pela comunidade técnica, os capacitores originais de fábrica estufam, perdem capacitância e causam picos de tensão que destroem integrados importantes (como os MOSFETs de chaveamento das lâmpadas CCFL e o chip amplificador de áudio `TPA3005D2`, deixando o aparelho completamente mudo ou inoperante).

---

## 📺 Modelos Doadores Compatíveis (Substituição de Painel)

Para recuperar o seu monitor de 15 kHz sem precisar trocar a película, você pode extrair o painel LCD íntegro de outros modelos comuns de mercado que utilizam a mesma furação, conector LVDS e pinagem de lâmpadas. 

| Seu Monitor Original | Modelo Doador Recomendado (LG) | Modelo do Painel Interno | Observações de Compatibilidade |
| :--- | :--- | :--- | :--- |
| **M1721A** (17") | LG Flatron L1752S / L1753S / L1718S | LM170E01 (ou equivalente) | Plug and play na furação e cabo LVDS; verificar apenas o comprimento dos cabos das lâmpadas CCFL. |
| **M1921A** (19") | LG Flatron L1952S / L1953S / L192WS | LM190E01 (ou equivalente) | Compatibilidade direta de sinal e fixação. Atenção à versão do painel (revisão de pinagem). |

---

## 🛠️ Lista de Componentes para Substituição (Recap & Reparo)

Antes de realizar a troca do painel LCD, é mandatório efetuar o *recap* (substituição dos capacitores eletrolíticos) para estabilizar as tensões do monitor. Abaixo está a tabela de referência com os componentes necessários para as placas interna da fonte e analógica (principal).

### Placa da Fonte de Alimentação (Power Board)
> **Atenção:** Recomenda-se estritamente o uso de capacitores com certificação de **105°C** e baixo ESR para garantir a durabilidade.

| Referência no Circuito | Componente Original | Função / Setor | Componente p/ Substituição Recomendado |
| :--- | :--- | :--- | :--- |
| **C202** | 680 µF / 25V | Filtragem de Linha / Inverter | 680 µF ou 1000 µF / 25V (105°C) |
| **C203** | 1000 µF / 25V | Filtragem Principal da Fonte | 1000 µF / 25V (105°C) |
| **C204** | 1000 µF / 16V | Linha de Baixa Tensão (5V / 3.3V) | 1000 µF / 16V ou 25V (105°C) |
| **C205** | 1000 µF / 16V | Linha de Baixa Tensão (5V / 3.3V) | 1000 µF / 16V ou 25V (105°C) |
| **C206** | 680 µF / 25V | Filtragem de Linha / Inverter | 680 µF ou 1000 µF / 25V (105°C) |
| **U406 (Opcional)** | SI4925 / P2103NVG | CI MOSFET de Chaveamento | Substituir apenas se a tela piscar e apagar |

### Placa Analógica / Principal (Main Board)
> Setor responsável pelo processamento de vídeo de 15 kHz e o circuito integrado de áudio, que costuma queimar devido a falhas na filtragem.

| Referência no Circuito | Componente Original | Função / Setor | Componente p/ Substituição Recomendado |
| :--- | :--- | :--- | :--- |
| **C800 a C810 (Setor)**| Vários (Eletrolíticos pequenos) | Filtragem de Sinais de Vídeo | Substituir por equivalentes de mesma capacitância (105°C) |
| **IC (Áudio)** | TPA3005D2 | Amplificador de Áudio Integrado | Substituir em caso de ausência total de som / curto |
| **ZD102 / ZD136** | Diodo Zener 5.6V | Proteção das Entradas de Vídeo | Diodo Zener 5.6V (Substituir se houver tela preta nas entradas) |

---

## 📂 Estrutura do Repositório

* `/manuais/` - Manuais de serviço oficiais em formato PDF.
* `/esquemas/` - Diagramas das placas de circuito impresso.
* `/fotos/` - Registros fotográficos do processo de desmontagem e adaptação do novo LCD doador.

---
*Contribuições para o mapeamento de mais revisões de placas e modelos de monitores doadores são sempre bem-vindas! Crie uma **Issue** ou envie um **Pull Request**.*
