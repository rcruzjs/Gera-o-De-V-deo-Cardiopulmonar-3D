---
name: recriar-video-cardiopulmonar
description: Gera e recria videos cientificos em 3D de alta fidelidade do corpo humano com transparencia em camadas, foco cardiopulmonar e HUD medico, parametrizado dinamicamente pelos resultados de exames funcionais dos pacientes (TCPE, ergoespirometria, ecocardiograma). Use quando o usuario pedir para gerar, recriar ou adaptar esse video medico 3D com dados de pacientes.
---

# Reproducao de Video Cardiopulmonar 3D Parametrizado

Esta skill padroniza a geracao e reproducao de videos cientificos em 3D do corpo humano com camadas anatomicas translucidas, foco no sistema cardiopulmonar e projecao de metricas clinicas (HUD), adaptando a dinamica fisiologica e os dados visuais aos resultados dos exames de cada paciente.

## Quando Utilizar

- O usuario solicita reproduzir ou recriar o video medico 3D mantendo o mesmo design, transparencia, anatomia 3D e estetica cientifica.
- O usuario fornece novos resultados de exames funcionais (Teste Cardiopulmonar de Esforco - TCPE, ergoespirometria, teste ergometrico ou ecocardiograma) para gerar um video personalizado para um paciente.
- O usuario pede para ajustar metricas ou comportamentos fisiologicos no video anterior.

## Fluxo de Trabalho

1. **Extracao de Parametros do Paciente:** Identifique no prompt ou no laudo do paciente as variaveis funcionais disponiveis:

   - Consumo de oxigenio: `VO2_PICO` (mL/kg/min)
   - Frequencia cardiaca: `FC_PICO` (bpm) e `FC_MAX_PREVISTA` (bpm)
   - Pressao arterial no esforco: `PA_PICO` (mmHg)
   - Eficiencia de transporte: `PULSO_O2` (mL/bat)
   - Eficiencia ventilatoria: `SLOPE_VE_VCO2`
   - Ritmo eletrico e funcao contratil: `RITMO_CARDIACO` (ex: ritmo sinusal normal)

2. **Mapeamento Visual e Fisiologico:** Traduza os valores numericos do paciente em comportamento visual anatomico (consulte `references/mapeamento-fisiologico.md` para regras detalhadas):

   - A cadencia contratil do miocardio e o fluxo sanguineo 3D devem refletir o ritmo e a resposta cronotropica (`FC_PICO` / `RITMO_CARDIACO`).
   - A iluminacao de difusao alveolar nos pulmoes deve refletir a eficiencia ventilatoria (`SLOPE_VE_VCO2` e `VO2_PICO`).

3. **Construcao do Prompt Padronizado (em Ingles):** Monte o prompt para a ferramenta `video_generation:generate_video_from_inputs` seguindo rigorosamente o template de design, transparencia e camadas 3D documentado em `references/especificacoes-visuais-3d.md`.

4. **Verificacao de Restricoes Visuais:**

   - Mantenha foco exclusivo no torax, coracao, vasos da base e pulmoes em 3D translucido.
   - Exclua explicitamente imagens de joelhos, articulacoes inferiores ou lesoes ortopedicas.
   - Sempre envie o prompt para a ferramenta em ingles e responda ao usuario em portugues.

## Template Base de Geracao (Prompt Master)

Utilize a estrutura abaixo ao acionar `video_generation:generate_video_from_inputs`, substituindo as variaveis entre colchetes pelos dados reais do paciente (ou mantendo os valores de referencia caso o usuario nao informe novos numeros):

3D medical and scientific visualization of the human body torso with glass-like anatomical layer transparency, translucent skin and ribcage revealing detailed 3D lungs breathing and a functioning heart beating in [RITMO_CARDIACO] with educational and scientific rigor, dynamic hemodynamic blood flow and oxygen diffusion lighting, excluding any knee images or orthopedic injuries, projecting a clean medical holographic HUD with cardiopulmonary exercise test data: peak VO2 [VO2_PICO] mL/kg/min, peak heart rate [FC_PICO] bpm, maximum heart rate [FC_MAX] bpm, blood pressure [PA_PICO] mmHg, O2 pulse [PULSO_O2] mL/beat, and VE/VCO2 slope [SLOPE_VE_VCO2]

## Recursos e Artefatos Auxiliares

- `references/especificacoes-visuais-3d.md`: Diretrizes exatas de design, shaders de transparencia, camadas anatomicas e iluminacao para manter fidelidade visual absoluta entre videos.
- `references/mapeamento-fisiologico.md`: Tabela de conversao de resultados medicos funcionais dos pacientes para dinamica visual 3D.
- `assets/exemplos-clinicos.md`: Exemplos completos de prompts e parametrizacoes para diferentes perfis clinicos (referencia padrao, atleta de alta performance e reabilitacao).