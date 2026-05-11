# 🛣️ Challenge CCR Motiva: Zeladoria Digital & Monitoramento de Vegetação

## 👥 Integrantes do Grupo (São Paulo, SP - 2026)
* **Enzo Ribeiro Domingues Piazentin** - RM: 564216
* **Guilherme Domingues Califoni** - RM: 565157
* **Antonio Lucas Santana Tavares** - RM: 56551
* **Lucas M.** - RM: 563677
* **Gustavo Schimith** - RM: 564800

---

## 🎯 1. O Problema Escolhido
A Motiva enfrenta um grande gargalo na gestão da vegetação nas margens de suas rodovias e ferrovias. O processo atual é analógico, dependendo de inspeções visuais ("a olho") e do preenchimento manual de pranchetas de papel que depois são transcritas para o Excel (o exaustivo *double data entry*). 

Esse atraso na comunicação causa intervenções tardias, resultando em mato alto que esconde animais, prejudica a sinalização, coloca motociclistas em risco e, criticamente, gera risco iminente de multas pesadas por parte das agências reguladoras.

---

## 👤 2. Persona Principal
**João, o Operador de Campo (Equipe de Roçada)**
* **O que faz:** Dirige o caminhão de manutenção e opera a roçadeira nas rodovias.
* **Dores:** Perde tempo tentando encontrar o quilômetro exato onde o mato está alto, sofre com ordens de serviço de papel que chegam atrasadas e sente frustração com a falta de comunicação clara com a base.
* **Necessidade:** Uma ferramenta direta que o guie ao local exato do problema de forma rápida e visual, sob a luz do sol, sem burocracias.

---

## 💡 3. Proposta de Solução (Fluxo de Ponta a Ponta)
Nossa solução substitui a prancheta por automação e inteligência, dividida em três frentes:

1. **Entrada de Dados (Câmera):** Aproveitamos as câmeras já instaladas no teto dos veículos da Motiva. Uma API de visão computacional analisa os frames em tempo real para calcular a altura da grama e atrela essas medições às coordenadas de GPS do carro, enviando os dados automaticamente para a nuvem.
2. **Processamento (Sistema Web):** O cérebro da operação. Um algoritmo classifica o risco do mato (Estável, Atenção, Crítico) e cruza esses dados para gerar um cronograma automático de prioridades, exibindo um mapa de calor (*heatmap*) para o gestor.
3. **Saída (App Mobile "Motiva Field"):** O aplicativo focado no João (operador). Ele recebe as ordens geolocalizadas do dia, utiliza o GPS para navegação guiada até o trecho crítico e possui um botão de "Serviço Concluído" que retroalimenta o sistema Web em tempo real.

---

## ⚙️ 4. Documento de Requisitos

### Requisitos Funcionais (RF)
* **RF01:** O sistema deve receber e armazenar os dados de altura da vegetação em centímetros e suas respectivas coordenadas GPS geradas pela câmera.
* **RF02:** O sistema web deve possuir um algoritmo capaz de classificar as áreas coletadas em diferentes níveis de risco (ex: Estável, Atenção, Crítico).
* **RF03:** O sistema web deve apresentar um mapa de calor (*heatmap*) interativo para os gestores visualizarem os pontos críticos da rodovia.
* **RF04:** O sistema web deve gerar despachos/ordens de serviço e enviá-los diretamente para o aplicativo mobile da equipe de campo.
* **RF05:** O aplicativo mobile deve exibir uma lista de ordens de serviço priorizadas por risco e distância.
* **RF06:** O aplicativo mobile deve possuir navegação via GPS para guiar o operador até a coordenada exata da vegetação alta.
* **RF07:** O aplicativo mobile deve possuir um botão para confirmação de "Serviço Concluído", que deve atualizar o status da via no banco de dados central em tempo real.

### Requisitos Não Funcionais (RNF)
* **RNF01 (Usabilidade):** O aplicativo mobile deve possuir alto contraste visual (Modo Claro padrão, botões grandes e cores indicativas) para garantir a leitura impecável sob a luz solar direta na rodovia.
* **RNF02 (Acessibilidade):** O aplicativo deve possuir fluxo linear, sem menus inferiores complexos, permitindo o uso rápido por operadores que possam estar utilizando luvas de proteção.
* **RNF03 (Desempenho):** A sincronização de dados entre a confirmação do app mobile e a atualização do dashboard web deve ocorrer com latência mínima, garantindo a gestão em tempo real.
* **RNF04 (Plataforma):** O aplicativo móvel deve ser compatível e executável nativamente tanto em dispositivos Android quanto iOS.

---

## 💻 5. Stack Tecnológica e Justificativa

* **React Native & Expo (Front-end Mobile):** Escolhidos pela facilidade de desenvolver um aplicativo robusto para Android e iOS utilizando um único código-base em JavaScript/TypeScript. O Expo facilita absurdamente a integração rápida com a API de GPS nativa do dispositivo, essencial para a funcionalidade de navegação do nosso projeto.
* **Supabase (Backend-as-a-Service & Banco de Dados):** Selecionado para atuar como o nosso banco de dados relacional (PostgreSQL) na nuvem. Sua vantagem principal é a capacidade de atualizações *real-time* (WebSockets), o que é vital para que o clique de "Serviço Concluído" no campo atualize imediatamente o mapa na tela do gestor.
* **Figma (Prototipação):** Escolhido para a criação do protótipo de alta fidelidade e navegável, permitindo validar a jornada do usuário e o contraste das cores corporativas antes da codificação.

---

## 🚀 6. Protótipo Navegável

🔗 **[INSERIR AQUI O LINK PÚBLICO DO FIGMA]**

*(Nota para o avaliador: O protótipo é totalmente navegável. Siga o fluxo principal clicando nos botões interativos para simular a jornada de campo).*
