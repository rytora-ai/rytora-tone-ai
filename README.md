# 🎸 RYTORA TONE AI  
### _Your perfect tone. Any device._

---

## 🚀 Sobre o Projeto

**Rytora Tone AI** é uma plataforma universal de **Inteligência Artificial e Modelagem Neural** para guitarristas e produtores musicais.  
Ela combina tecnologias de IA generativa, controle MIDI/USB, e o **Neural Amp Modeler (NAM)** para criar, treinar e converter timbres de guitarra de forma automática.

> “Seu timbre perfeito. Qualquer pedaleira.”

---

## 🧠 Visão Geral

O projeto nasceu para resolver um problema recorrente entre músicos e produtores:
- Criar e migrar timbres entre pedaleiras diferentes é difícil e demorado.
- Cada plataforma (Quad Cortex, Helix, Fractal, Kemper) tem seu formato e timbre próprio.
- Capturar o "som ideal" exige experiência e muito tempo.

**Rytora Tone AI** automatiza esse processo com IA:
1. Gera timbres completos a partir de estilo, guitarra e artista.  
2. Aplica o preset automaticamente em qualquer pedaleira via MIDI/USB.  
3. Permite treinar e importar modelos **NAM** (Neural Amp Modeler) com fidelidade real.  
4. Converte presets entre marcas (ex.: QC → Helix → Fractal).  
5. Ajusta o timbre em tempo real com comandos em linguagem natural.

---

### **Camadas Principais**

| Camada | Descrição |
|--------|------------|
| **Electron App** | Interface desktop em Node.js + TypeScript |
| **AI Tone Engine** | IA generativa que cria cadeias e presets |
| **NAM Engine** | Núcleo neural (treinamento, execução e blending NAM) |
| **Driver Framework** | Drivers universais para Quad Cortex, Helix, Fractal, Kemper, etc. |
| **Bridge Nativo** | Comunicação Node ↔ Python/C++ via FastAPI |
| **Licenciamento SaaS** | Ativação, planos e controle de assinaturas |
| **Cloud Library** | Upload, busca e compartilhamento de modelos NAM |

---

## 📂 Estrutura de Pastas

```
/electron
/src/main
/src/renderer
/src/drivers
/src/ai
/src/tone
/src/ipc
/src/ui
/native
/python
/nam/
trainer/
player/
manager/
/bridge/
/cpp
/backend-licensing
/docs
```


---

## 🔌 Integrações Principais

### **1. IA Generativa (AIPresetPlan)**
- Recebe: estilo, guitarra, papel, artista  
- Gera: cadeia completa com amps, drives, delays, reverbs e cenas  
- Exporta: `AIPresetPlan` em JSON  
- Compatível com drivers de múltiplas pedaleiras  

### **2. NAM Integration (Neural Amp Modeler)**
- Treina e executa modelos NAM locais via PyTorch/ONNX  
- Permite capturas personalizadas e mixagem neural  
- IA escolhe o modelo NAM ideal por estilo/artista  
- Módulos:
  - `namTrainer.py` → Treina e salva `.nam`
  - `namPlayer.py` → Executa modelo em tempo real
  - `namManager.ts` → Organiza, importa e aplica modelos
  - `namBridge.ts` → Comunicação Node ↔ Python (FastAPI)

### **3. Multi-Pedaleira (Drivers Universais)**
- Drivers independentes (`quad-cortex`, `helix`, `fractal`, `kemper`)  
- Auto-detecção via MIDI/USB  
- Conversão automática de timbres entre formatos (.hlx, .syx, .kipr, .qcp)  
- Exportação de presets nativos  

### **4. Controle e Automação**
- Comunicação via MIDI e SysEx  
- Suporte a Program Change e Control Change  
- Ajuste em tempo real via IA: “mais brilho”, “menos drive” etc.

### **5. Licenciamento e SaaS**
- Sistema de ativação com planos:
  - Lite – R$19/mês  
  - Pro – R$49/mês  
  - Studio – R$89/mês  
- Verificação periódica (online/offline)
- API de backend em NestJS/Express

---

## 🧩 Fluxo de Operação

```
Usuário → Escolhe estilo, guitarra e pedaleira
↓
AI Preset Generator → Cria AIPresetPlan
↓
AI NAM Selector → Adiciona modelos NAM
↓
Tone Engine → Aplica TonePlan via Bridge
↓
Pedalboard Driver (QC / Helix / Fractal / Kemper)
↓
Execução via MIDI / USB
```


---

## ⚙️ Tecnologias Utilizadas

| Área | Tecnologia |
|------|-------------|
| App | Electron + TypeScript |
| Backend Local | Node.js + Express |
| IA | OpenAI / Claude + Regras Locais |
| Modelagem Neural | Neural Amp Modeler (PyTorch / ONNX) |
| Áudio | sounddevice / pyaudio |
| Controle | MIDI / SysEx / USB (libusb / pyusb) |
| UI | React + Tailwind (renderer Electron) |
| Licenciamento | JWT + API NestJS |
| Persistência | SQLite / PostgreSQL (SaaS) |

---

## 🧠 IA e Machine Learning

### Principais módulos:
- `aiPresetGenerator.ts` → Cria presets por estilo  
- `aiNAMSelector.ts` → Escolhe modelos NAM adequados  
- `aiRealtimeAdjuster.ts` → Ajuste fino dinâmico  
- `aiPresetMigration.ts` → Migração entre pedaleiras  
- `aiNAMMixer.ts` → Mistura neural de modelos NAM

A IA combina:
- Regras determinísticas (fallback engine)  
- Modelos generativos (LLM)  
- Algoritmos de equivalência de timbres  

---

## 🎛️ Funcionalidades Principais

- ✅ Geração automática de timbres por IA  
- ✅ Treinamento e execução de modelos NAM  
- ✅ Compatibilidade universal com pedaleiras  
- ✅ Controle real-time via MIDI e USB  
- ✅ Migração entre plataformas (QC ↔ Helix ↔ Fractal)  
- ✅ Ajuste fino por comandos em linguagem natural  
- ✅ Biblioteca cloud de modelos NAM  
- ✅ Sistema de licenciamento com planos SaaS  
- ✅ UI moderna e responsiva em Electron  

---

## 💡 Roadmap

| Fase | Entregável | Status |
|------|-------------|--------|
| Fase 1 | App base (Electron + Node) | ✅ |
| Fase 2 | MIDI Bridge (Quad Cortex) | ✅ |
| Fase 3 | IA estrutural (Tone Engine) | ✅ |
| Fase 4 | NAM Engine (Trainer + Player) | 🚧 |
| Fase 5 | Drivers Universais | 🚧 |
| Fase 6 | IA multi-device e migração | 🚧 |
| Fase 7 | Cloud NAM Library + Marketplace | 🔜 |
| Fase 8 | Lançamento SaaS (Rytora Cloud) | 🔜 |

---

## 🧩 API Local (Resumo)

### `/qc/program-change`

POST `{ "program": 10 }`

### `/nam/load_model`

POST `{ "file": "models/Fender.nam" }`

### `/nam/train`

POST `{ "dataset": "captures/Fender_65", "epochs": 50 }`

### `/ai/generate-preset`

POST `{ "style": "Worship", "guitar": "HH", "artist": "Mateus Asato" }`


---

## 🪪 Licenciamento

**Sistema de ativação Rytora Tone AI**

- O usuário ativa via chave e e-mail.  
- Licenças:
  - Lite – 1 dispositivo  
  - Pro – 3 dispositivos  
  - Studio – ilimitado  
- Renovação automática mensal/anual  
- Suporte offline temporário (cache local)

---

## 🧰 Requisitos para Desenvolvimento

### Ambiente
- Node.js ≥ 20.0  
- Python ≥ 3.10  
- Git + npm + pip  
- GPU opcional (CUDA/ROCm)  

### Setup
```bash
git clone https://github.com/rytora-ai/rytora-tone-ai.git
cd rytora-tone-ai
npm install
npm run dev
```
Para instalar dependências Python:
```bash
cd native/python
pip install -r requirements.txt
```

## 🔒 Legal

Rytora Tone AI é uma plataforma independente.

> “Quad Cortex”, “Helix”, “Fractal”, “Kemper” e outras marcas são propriedades de seus respectivos fabricantes.
> Este software não é afiliado, endossado ou patrocinado por nenhuma dessas empresas.

🏢 Sobre a Rytora

## Rytora – AI Technology & Solutions Ltda
## 🚀 Inovando em Inteligência Artificial aplicada a áudio, automação e soluções SaaS.
🌐 rytora.ai
📧 contact@rytora.ai
