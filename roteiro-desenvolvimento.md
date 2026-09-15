# Roteiro de Desenvolvimento — Iniciação Científica

## Princípio central

> **O estudante desenvolve o jogo; a plataforma CIATEC define o experimento.**

Cada estudante escolhe um paradigma de jogo diferente, porém todos desenvolvem sobre a mesma arquitetura, infraestrutura experimental e ciclo de desenvolvimento.

```text
GDD
 ↓
Unity
 ↓
Calibration
 ↓
Level Design
 ↓
Gameplay
 ↓
Telemetry
 ↓
Results
 ↓
Research API
```

---

## FASE 0 — Fundamentação

1. Escolha do paradigma de jogo.
2. Levantamento bibliográfico.
3. Definição do problema/pergunta de pesquisa.
4. Definição das variáveis que o jogo deverá observar.
5. Estudo dos paradigmas de game design e serious games.

---

## FASE 1 — Especificação

6. Elaboração do **Game Design Document (GDD)**.
7. Definição da arquitetura padrão:

```text
Login → Menu → Settings → Gameplay → Results
```

8. Definição das variáveis experimentais:
   - **Control Calibration** — sensibilidade, limites, thresholds etc.
   - **Level Design** — dificuldade, velocidade, quantidade, tempo, precisão etc.
   - **Gameplay** — regras e condições da tarefa.
   - **Results** — indicadores derivados.
   - **Telemetry** — eventos e comportamento de utilização.

9. Definição do modelo de dados e dos eventos de telemetria.

---

## FASE 2 — Gestão do Projeto

10. Transformar o GDD em **GitHub Project**.
11. Criar Issues, milestones e backlog.
12. Definir sprints.
13. Estabelecer critérios de aceite.
14. Versionamento pelo Git/GitHub.

---

## FASE 3 — Desenvolvimento do Núcleo

15. Criar o projeto Unity a partir do template institucional.
16. Implementar:

```text
Menu → Settings → Gameplay → Results
```

17. Integrar o package institucional de autenticação como infraestrutura prevista.
18. Criar o sistema de **configuração/calibração**.
19. Criar o sistema de **Level Design parametrizado**.

---

## FASE 4 — Telemetria

20. Implementar **Event Telemetry**:

```text
Start → Action → Success/Failure → Pause → Restart → Finish
```

21. Implementar **Usage Telemetry**:
   - teclado;
   - mouse;
   - touch;
   - gamepad;
   - sensores inerciais;
   - tempo;
   - frequência;
   - sequência das ações.

22. Garantir que todos os dados sejam registrados em um modelo comum.

---

## FASE 5 — Resultados

23. Definir as variáveis de resultado.
24. Implementar o cálculo dos indicadores.
25. Criar a tela **Results**.
26. Validar se os resultados podem ser reconstruídos exclusivamente pela telemetria.

---

## FASE 6 — Arte

27. Definir a identidade visual no GDD.
28. Selecionar assets no Freepik.
29. Adaptar/criar os assets.
30. Integrar a arte ao gameplay sem alterar a camada experimental.

---

## FASE 7 — Mock Research Backend

31. Criar dados mockados de:
   - usuário;
   - sessão;
   - configuração;
   - level;
   - eventos;
   - telemetria;
   - resultados.

32. O jogo funciona **100% offline utilizando o mock**.

---

## FASE 8 — Validação

33. Testes funcionais.
34. Testes de telemetria.
35. Testes de reprodutibilidade dos resultados.
36. Testes de usabilidade.
37. Playtest.
38. Ajustes de balanceamento.

---

## FASE 9 — Integração Científica

39. Substituir o mock pela **Research API**.
40. Integrar autenticação real.
41. Enviar sessões e telemetria.
42. Receber configurações/experimentos.
43. Validar o fluxo completo:

```text
Research System
      ↓
     Game
      ↓
  Gameplay
      ↓
  Telemetry
      ↓
   Results
      ↓
Research System
```

---

## FASE 10 — Produção Científica

44. Análise dos dados.
45. Resultados experimentais.
46. Discussão.
47. Relatório de IC.
48. Artigo/pôster/congresso.
49. Repositório técnico documentado.

---

## Arquitetura Experimental Comum

Todos os jogos devem compartilhar a mesma estrutura conceitual:

```text
┌─────────────────────┐
│      Login          │
│  (infraestrutura)   │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│       Menu          │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│      Settings       │
│ Calibration/Config  │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│      Gameplay       │
│                     │
│ Level Design        │
│ Game Mechanics      │
│ Event Telemetry     │
│ Usage Telemetry     │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│      Results        │
│  Derived Metrics     │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│   Research System   │
│        API          │
└─────────────────────┘
```

## Regra de Desenvolvimento

O **jogo é a interface experimental**.

A infraestrutura deve separar:

- **o que o participante faz**;
- **como o jogo controla a tarefa**;
- **o que é registrado**;
- **como os indicadores são calculados**;
- **como os dados chegam ao sistema de pesquisa**.

Dessa forma, diferentes paradigmas podem ser comparados utilizando uma estrutura tecnológica e metodológica comum.
