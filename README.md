# **Qwen-Image-Edit-3D-Lighting-Control**

> A Gradio-based demonstration for the Qwen/Qwen-Image-Edit-2509 model with 3D lighting control using the Multi-Angle-Lighting LoRA adapter. Allows precise control of light source direction via interactive 3D viewport or sliders for azimuth and elevation. Supports fast inference (4 steps default) with Flash Attention 3, bfloat16, and dynamic prompt generation. Features auto-resizing (multiples of 8 up to 1024px), custom OrangeRed theme, and responsive layout.

https://github.com/user-attachments/assets/22dad2d5-70b4-4950-bcf5-5193dda6a7c9

---

<img width="753" height="630" alt="Screenshot 2026-02-04 132347" src="https://github.com/user-attachments/assets/7b0ed744-fe53-45dd-addb-0cef558e5ccb" />
<img width="1549" height="806" alt="Screenshot 2026-02-04 132402" src="https://github.com/user-attachments/assets/43730af7-a4a2-422f-97a3-d2e0afcb86e1" />

<img width="726" height="633" alt="Screenshot 2026-02-04 132539" src="https://github.com/user-attachments/assets/8f25d0df-d61a-4e9e-bf70-ff89943fad99" />
<img width="1506" height="811" alt="Screenshot 2026-02-04 132550" src="https://github.com/user-attachments/assets/8242c4bc-ac4d-49f7-a689-067e10347457" />

---

## Features
- **3D Lighting Control**: Interactive Three.js viewport with draggable handles for azimuth (horizontal) and elevation (vertical) angles; snaps to predefined positions (e.g., Front, Right, Above).
- **Slider Controls**: Manual adjustment for azimuth (0-315°) and elevation (-90-90°) with real-time prompt preview.
- **Lazy LoRA Loading**: Multi-Angle-Lighting adapter loads on first use to minimize VRAM.
- **Rapid Inference**: 4-step default with bfloat16 on CUDA; supports up to 20 steps.
- **Auto-Resizing**: Preserves aspect ratio, snaps to multiples of 8 (up to 2048px).
- **Custom Theme**: OrangeRedTheme with clean, responsive design.
- **Prompt Generation**: Dynamically builds lighting prompts (e.g., "Light source from the Front").
- **Queueing**: Up to default Gradio queue limits for concurrent jobs.

## Prerequisites
- Python 3.10 or higher.
- CUDA-compatible GPU (required for bfloat16 and Flash Attention 3).
- Stable internet for initial model/LoRA downloads.

## Installation
1. Clone the repository:
   ```
   git clone https://github.com/PRITHIVSAKTHIUR/Qwen-Image-Edit-3D-Lighting-Control.git
   cd Qwen-Image-Edit-3D-Lighting-Control
   ```
2. Install dependencies:
   First, install pre-requirements:
   ```
   pip install -r pre-requirements.txt
   ```
   Then, install main requirements:
   ```
   pip install -r requirements.txt
   ```
   **pre-requirements.txt content:**
   ```
   pip>=23.0.0
   ```
   **requirements.txt content:**
   ```
   git+https://github.com/huggingface/accelerate.git
   git+https://github.com/huggingface/diffusers.git
   git+https://github.com/huggingface/peft.git
   transformers==4.57.3
   huggingface_hub
   sentencepiece
   torchvision
   kernels
   spaces
   hf_xet
   gradio #gradio@6
   torch==2.8.0
   numpy
   av
   ```
3. Start the application:
   ```
   python app.py
   ```
   The demo launches at `http://localhost:7860`.

## Usage
1. **Upload Image**: Add an image via the input component.
2. **Control Lighting**: Use the 3D viewport (drag yellow/blue handles) or sliders for azimuth/elevation.
3. **Preview Prompt**: View auto-generated lighting prompt; edit if needed.
4. **Configure (Optional)**: Adjust seed, guidance scale, steps, height/width in Advanced Settings.
5. **Generate**: Click "Generate Image" to produce output.

### Supported Adapters
| Adapter             | Use Case                          |
|---------------------|-----------------------------------|
| Multi-Angle-Lighting | Precise directional lighting control |

## Troubleshooting
- **Adapter Loading**: First run downloads LoRA; monitor console.
- **OOM**: Reduce steps/resolution; clear cache with `torch.cuda.empty_cache()`.
- **Flash Attention Fails**: Fallback to default; requires compatible CUDA.
- **No Output**: Ensure image uploaded and prompt valid; check console.
- **3D Viewport Issues**: Ensure browser supports WebGL/Three.js.

## Contributing
Contributions welcome! Add new adapters to `ADAPTER_SPECS`, enhance 3D controls, or improve prompts. Submit pull requests via the repository.

Repository: [https://github.com/PRITHIVSAKTHIUR/Qwen-Image-Edit-3D-Lighting-Control.git](https://github.com/PRITHIVSAKTHIUR/Qwen-Image-Edit-3D-Lighting-Control.git)

## License
Apache License 2.0. See [LICENSE](LICENSE) for details.
Built by Prithiv Sakthi. Report issues via the repository.
