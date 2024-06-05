

# 🚀 Options to use Clarity-Upscaler

# Notebook  https://colab.research.google.com/drive/1q9JTywiev1gEXt2_OcQh1TIJKNSiqjdj?usp=sharing

## 🧑‍💻 App

The simplest option to use Clarity is with the app at [ClarityAI.co](https://ClarityAI.co)

## 🐰 ComfyUI

1. Open ComfyUI Manager, search for Clarity AI, and install the node.
2. Create an API key at: [ClarityAI.co/ComfyUI](https://ClarityAI.co/comfyui)
3. Add the API key to the node as a) envirement variable `CAI_API_KEY` OR b) to a `cai_platform_key.txt` text file OR c) in `api_key_override` field of the node.

Full instructions: https://github.com/philz1337x/ComfyUI-ClarityAI

## ⚙️ API

Use the API at: [ClarityAI.co/API](https://ClarityAI.co/api)

## Advanced: Deploy and run with cog (locally or cloud)

If you are not familiar with cog read: <a href=https://github.com/replicate/cog/blob/main/docs/getting-started-own-model.md>cog docs</a>

- Download Checkpoints and LoRa's from Cvitai and put in /models folder (a download_weights.py file to prepare everything with one file is a work in progress)

```
https://civitai.com/models/46422/juggernaut
https://civitai.com/models/82098?modelVersionId=87153
https://civitai.com/models/171159?modelVersionId=236130
```

- predict with cog:

```su
cog predict -i image="link-to-image"
```

## Advanced: Run with A1111 webUI

https://github.com/AUTOMATIC1111/stable-diffusion-webui

- Use these params:

```Prompt:
masterpiece, best quality, highres, <lora:more_details:0.5> <lora:SDXLrender_v2.0:1> Negative prompt: (worst quality, low quality, normal quality:2) JuggernautNegative-neg Steps: 18, Sampler: DPM++ 3M SDE Karras, CFG scale: 6.0, Seed: 1337, Size: 1024x1024, Model hash: 338b85bc4f, Model: juggernaut_reborn, Denoising strength: 0.35, Tiled Diffusion upscaler: 4x-UltraSharp, Tiled Diffusion scale factor: 2, Tiled Diffusion: {"Method": "MultiDiffusion", "Tile tile width": 112, "Tile tile height": 144, "Tile Overlap": 4, "Tile batch size": 8, "Upscaler": "4x-UltraSharp", "Upscale factor": 2, "Keep input size": true}, ControlNet 0: "Module: tile_resample, Model: control_v11f1e_sd15_tile, Weight: 0.6, Resize Mode: 1, Low Vram: False, Processor Res: 512, Threshold A: 1, Threshold B: 1, Guidance Start: 0.0, Guidance End: 1.0, Pixel Perfect: True, Control Mode: 1, Hr Option: HiResFixOption.BOTH, Save Detected Map: False", Lora hashes: "more_details: 3b8aa1d351ef, SDXLrender_v2.0: 3925cf4759af"
```
