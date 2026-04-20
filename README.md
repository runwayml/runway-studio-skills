# Runway Studio Skills

A Claude/Cursor agent skill for generating studio-quality videos, images, and audio using the [Runway API](https://docs.dev.runwayml.com/).

## Setup

1. Get a Runway API key from [runway.com](https://app.runwayml.com/)
2. Set your API key:

```bash
export RUNWAYML_API_SECRET="your-api-key"
```

3. Install [uv](https://docs.astral.sh/uv/getting-started/installation/) (if not already available — it ships with Claude Code):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## Usage

All scripts are standalone Python CLIs runnable via `uv run` — no manual dependency installation needed.

| Script | Purpose |
|--------|---------|
| `scripts/generate_video.py` | Text-to-video, image-to-video, video-to-video, character performance |
| `scripts/generate_image.py` | Text/image to image generation |
| `scripts/generate_audio.py` | Sound effects, TTS, speech-to-speech, voice dubbing, voice isolation |
| `scripts/get_task.py` | Poll, retrieve, or delete tasks |

### Quick examples

```bash
# Generate a video from text
uv run scripts/generate_video.py --prompt "A product bottle rotating slowly on a marble surface" --model seedance2 --ratio 720:1280 --duration 10

# Generate a video from an image
uv run scripts/generate_video.py --prompt "Smooth camera push-in" --image "https://example.com/product.jpg" --model seedance2

# Generate an image
uv run scripts/generate_image.py --prompt "Minimal skincare bottle on white background" --model gen4_image --ratio 1080:1080

# Generate a sound effect
uv run scripts/generate_audio.py sound-effect --prompt "Soft whoosh transition sound" --duration 3

# Check task status
uv run scripts/get_task.py --task-id "your-task-uuid" --poll
```

## Documentation

- **[SKILL.md](SKILL.md)** — Full agent skill reference (models, parameters, error handling)
- **[COOKBOOK.md](COOKBOOK.md)** — End-to-end recipes for product ads and campaigns

## License

MIT
