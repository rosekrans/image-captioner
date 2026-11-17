# joycaption

A simple script that uses the [JoyCaption](https://huggingface.co/fancyfeast/llama-joycaption-beta-one-hf-llava) model (a fine-tuned LLaVA based on Llama 3.1) to generate a long, formal descriptive caption for an image.

## Requirements

- Python 3.10+
- NVIDIA GPU with sufficient VRAM (the model is loaded in bfloat16 on `device_map=0`)
- CUDA-enabled PyTorch

```bash
# Install dependencies
# (Install a CUDA-compatible torch first if needed; see https://pytorch.org/get-started/locally/)
pip install -r requirements.txt
```

## Usage

1. Edit the script and set `IMAGE_PATH` to the image you want to caption.
2. Optionally change `PROMPT` or `MODEL_NAME`.
3. Run:

```bash
python caption.py
```

The caption is printed to stdout.

## Notes

- The model is downloaded automatically on first run from Hugging Face.
- This script assumes a CUDA GPU is available. CPU inference is possible but will be very slow and may require changes to `device_map` and dtypes.
- The chat-template handling for LLaVA models can be fragile; the combination used here is known to work with this specific model.

## License

MIT
