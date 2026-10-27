# Exemplos de Aplicacao por Perfil de Paciente

Abaixo estao exemplos praticos de como transformar dados clinicos de diferentes pacientes em prompts prontos para reproducao exata do video 3D.

---

## Exemplo 1: Paciente de Referencia (Padrao de Reproducao Exata)

**Dados do Paciente:**
- Ritmo: Sinusal normal
- VO2 pico: 25.57 mL/kg/min
- FC pico / FC max: 147 bpm / 157 bpm
- PA no pico: 176/60 mmHg
- Pulso de O2: 20.0 mL/bat
- Slope VE/VCO2: 24.7

**Prompt para `video_generation:generate_video_from_inputs`:**
3D medical and scientific visualization of the human body torso with glass-like anatomical layer transparency, translucent skin and ribcage revealing detailed 3D lungs breathing harmoniously and a functioning heart beating in normal sinus rhythm with strong systolic ejection and educational and scientific rigor, excluding any knee images or orthopedic injuries, projecting a clean medical holographic HUD with cardiopulmonary exercise test data and metrics: peak VO2 25.57 mL/kg/min, peak heart rate 147 bpm, maximum heart rate 157 bpm, blood pressure 176/60 mmHg, O2 pulse 20.0 mL/beat, and VE/VCO2 slope 24.7

---

## Exemplo 2: Paciente Atleta de Endurance (Alta Capacidade Aerobia)

**Dados do Paciente:**
- Ritmo: Sinusal normal, alta reserva cronotropica e inotropica
- VO2 pico: 58.4 mL/kg/min
- FC pico / FC max: 178 bpm / 180 bpm
- PA no pico: 190/70 mmHg
- Pulso de O2: 26.5 mL/bat
- Slope VE/VCO2: 21.2

**Prompt para `video_generation:generate_video_from_inputs`:**
3D medical and scientific visualization of the human body torso with glass-like anatomical layer transparency, translucent skin and ribcage revealing detailed 3D lungs with intense oxygen diffusion glow and a high-performance heart beating in normal sinus rhythm with powerful ventricular ejection and educational and scientific rigor, excluding any knee images or orthopedic injuries, projecting a clean medical holographic HUD with cardiopulmonary exercise test data and metrics: peak VO2 58.4 mL/kg/min, peak heart rate 178 bpm, maximum heart rate 180 bpm, blood pressure 190/70 mmHg, O2 pulse 26.5 mL/beat, and VE/VCO2 slope 21.2

---

## Exemplo 3: Paciente em Reabilitacao Cardiopulmonar (Limitacao Funcional Leve a Moderada)

**Dados do Paciente:**
- Ritmo: Sinusal regular com resposta cronotropica submaxima
- VO2 pico: 16.8 mL/kg/min
- FC pico / FC max: 118 bpm / 150 bpm
- PA no pico: 150/85 mmHg
- Pulso de O2: 11.5 mL/bat
- Slope VE/VCO2: 35.4

**Prompt para `video_generation:generate_video_from_inputs`:**
3D medical and scientific visualization of the human body torso with glass-like anatomical layer transparency, translucent skin and ribcage revealing detailed 3D lungs with rapid shallow ventilation and a functioning heart beating in regular sinus rhythm with moderate systolic contraction and educational and scientific rigor, excluding any knee images or orthopedic injuries, projecting a clean medical holographic HUD with cardiopulmonary exercise test data and metrics: peak VO2 16.8 mL/kg/min, peak heart rate 118 bpm, maximum heart rate 150 bpm, blood pressure 150/85 mmHg, O2 pulse 11.5 mL/beat, and VE/VCO2 slope 35.4