# Geração de Vídeo Cardiopulmonar 3D

Visualização científica 3D do tórax com **camadas anatômicas translúcidas**, foco cardiopulmonar e **HUD médico** parametrizado por resultados de Teste Cardiopulmonar de Esforço (TCPE / ergoespirometria).

🔗 **Demo ao vivo:** https://rcruzjs.github.io/Gera-o-De-V-deo-Cardiopulmonar-3D/

## Conteúdo

```
├── index.html                          # Animação 3D interativa (Three.js) — publicada no GitHub Pages
├── video-cardiopulmonar-paciente-f48.html
└── skill/recriar-video-cardiopulmonar/ # Skill para agentes de IA (Antigravity / Gemini)
    ├── SKILL.md
    ├── assets/       (exemplos clínicos, template de laudo)
    └── references/   (especificações visuais 3D, mapeamento fisiológico)
```

## Animação 3D

Abra `index.html` no navegador (requer internet para carregar o Three.js). Parâmetros mapeados:

| Parâmetro | Efeito visual |
|---|---|
| FC pico | Frequência real do batimento cardíaco e do ECG |
| Pulso de O₂ | Intensidade da ejeção sistólica na aorta |
| VO₂ pico | Brilho de difusão alveolar |
| Slope VE/VCO₂ | Padrão respiratório (fluido < 30, rápido/superficial ≥ 34) |
| Ritmo | Pulso de condução elétrica nó sinusal → ventrículos |

Para outro paciente, edite o objeto `P` no início do `<script>` e os valores dos cards do HUD.

## Instalando a skill

```bash
git clone https://github.com/rcruzjs/Gera-o-De-V-deo-Cardiopulmonar-3D.git
```

Copie `skill/recriar-video-cardiopulmonar/` para:
- **Projeto:** `.agents/skills/` na raiz do workspace, ou
- **Global:** `~/.gemini/config/skills/`

Depois use o template em `assets/template-entrada-rapida-laudo.md` para colar um laudo.

## ⚠️ Aviso

Material educacional. Não substitui avaliação médica. Não publique dados identificáveis de pacientes (LGPD).
