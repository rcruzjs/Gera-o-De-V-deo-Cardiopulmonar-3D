# Mapeamento de Parametros Medicos Funcionais para Dinamica Visual 3D

Este guia orienta como adaptar a descricao visual da animacao 3D de acordo com o resultado funcional do exame de cada paciente, mantendo o design base intacto.

## Tabela de Conversao Clinico-Visual

| Parametro Funcional | Significado Fisiologico | Impacto na Cena 3D e Prompt |
| :--- | :--- | :--- |
| **VO2 Pico** (`mL/kg/min`) | Capacidade aerobia maxima / captacao de O2 | Valores elevados (> 45) intensificam o brilho de difusao de oxigenio nos alveolos e capilares; valores reduzidos (< 20) geram iluminacao alveolar mais suave e contida. |
| **FC Pico / FC Maxima** (`bpm`) | Resposta cronotropica ao esforco | Define o ritmo visual de contracao ventricular na animacao (ex: `vigorous synchronous contractions` para FC alta vs `steady controlled contractions` para FC moderada). |
| **Pulso de O2** (`mL/bat`) | Volume sistolico indireto e extracao periferica | Valores altos (>= 15-20) sao representados por ejecao ventricular vigorosa na raiz da aorta (`strong systolic ejection wave`); curva achatada pede contracao mais curta. |
| **Slope VE/VCO2** | Eficiencia ventilatoria (relacao ventilacao/perfusao) | Slope < 30 indica alta eficiencia (expansao pulmonar fluida e harmonica); Slope >= 34 indica hiperventilacao relativa (expansao toracica rapida e superficial). |
| **Pressao Arterial** (`mmHg`) | Resposta inotropica e resistencia vascular | PA sistolica de esforco fisiologica (ex: 160-190/60-80 mmHg) destaca fluxo laminar pulsatil nas grandes arterias. |
| **Ritmo e ECG** | Conducao eletrica cardiaca | `normal sinus rhythm` projeta onda eletrica ordenada do no sinoatrial aos ventriculos; se houver arritmia descrita no laudo, adaptar para o ritmo correspondente. |

## Regras de Preenchimento de Dados Ausentes

1. **Laudo Completo:** Utilize todos os valores exatos fornecidos pelo usuario.
2. **Laudo Parcial:** Se o usuario fornecer apenas parte dos dados (ex: apenas VO2 pico e FC), inclua no prompt apenas as metricas informadas pelo paciente ou solicite confirmacao caso deseje manter os demais indicadores ocultos no HUD.
3. **Pedido de Reproducao Direta ("igual ao anterior"):** Utilize os parametros de referencia padrao:
   - VO2 pico: `25.57 mL/kg/min`
   - FC pico / maxima: `147 bpm` / `157 bpm`
   - Pressao arterial: `176/60 mmHg`
   - Pulso de O2: `20.0 mL/beat`
   - Slope VE/VCO2: `24.7`
   - Ritmo: `normal sinus rhythm`