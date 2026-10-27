# Especificacoes de Design, Transparencia e Anatomia 3D

Este artefato define os parametros visuais fixos que garantem que todo video gerado mantenha exatamente o mesmo padrao estetico, nivel de transparencia e rigor anatomico.

## 1. Arquitetura de Camadas e Transparencia (3D Layering)

- **Camada Externa (Epiderme e Contorno Toracico):** Renderizacao em estilo *glass-like* (vidro fosco/translucido azul-ciano escuro) com opacidade entre 15% e 25%, permitindo identificar a silhueta humana sem obstruir os orgaos internos.
- **Camada Intermediaria (Arcabouco Osseo e Parenquima Pulmonar):** Costelas, esterno e coluna toracica em semitransparencia (opacidade 30%), envolvendo pulmoes em 3D com textura bronquica e alveolar visivel, iluminados suavemente conforme a fase de inspiracao e expiracao.
- **Camada Central (Coracao e Grandes Vasos):** Opacidade de 90% a 100% com iluminacao de destaque (*subsurface scattering* realista no miocardio, coronarias, aorta, arteria pulmonar e veias cavas). Os feixes de conducao eletrica (no sinusal para atrios e ventriculos) exibem pulsos luminosos sincronizados com a sistole.

## 2. Iluminacao, Cor e Ambiente

- **Fundo (Background):** Ambiente clinico escuro (azul-marinho profundo a preto cientifico) para maximizar o contraste das camadas translucidas e dos dados projetados.
- **Paleta Fisiologica:**
  - Sangue arterial / oxigenado e difusao de O2: Vermelho rubi brilhante com reflexos dourados/alaranjados.
  - Sangue venoso / retorno sistemico: Azul ciano profundo.
  - Conducao eletrica sinusal: Feixes em branco-azulado ou amarelo-eletrico sutil.

## 3. Interface de Dados Medicos (HUD Cientifico)

- **Tipografia e Layout:** Projecao holografica limpa, plana e legivel ao redor do torax 3D, sem cobrir o miocardio em contracao.
- **Indicadores Obrigatorios:**
  - `VO2 peak` (mL/kg/min)
  - `Peak HR` / `Max HR` (bpm)
  - `BP` (mmHg)
  - `O2 Pulse` (mL/beat)
  - `VE/VCO2 Slope`

## 4. Restricoes Negativas (Negative Constraints)

- Nao incluir membros inferiores, articulacoes de joelho, proteses ou lesoes ortopedicas.
- Nao utilizar estilo cartunesco; manter rigor de visualizacao medica cientifica (padrao animacao biomedica de alta precisao).