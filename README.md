# Consistent Explainer Videos

### One topic. A clear story. The same approved visual style.

A reusable AI skill for turning a topic, article or infographic into a **60-second silent explainer video**. It packages the approved design, animation code, fonts, reference videos and quality checks so the team can produce a consistent series without redesigning each video.

**[Download the complete skill package](Consistent_Explainer_Videos_Skill.zip)**

## What this project is for

The goal is to make complex ideas easy to understand through a concrete example. Each video moves from **story → mechanism or framework → takeaway**, using readable sentences and animated UI demonstrations rather than dense slides.

The content changes with each topic. The visual identity and pacing stay fixed.

## What the output looks like

| Feature | Approved format |
| --- | --- |
| Deliverable | MP4 video |
| Duration | 60 seconds |
| Size | 1080 × 1350, portrait |
| Frame rate | 30 fps |
| Audio | Silent; no voice or music |
| Typography | Large serif scene leads, distinct compact uppercase header |
| Colours | Warm paper, deep green ink, yellow, pale blue and pale green |
| Motion | Staggered reveals, cursor interactions, gentle transitions and reading holds |
| Content | One illustrative story, 3–4 explanatory beats, a clear takeaway |

## Start here: review the examples

Download and extract the ZIP, then open these files inside `create-consistent-explainer-videos/`:

| Example | File to open | What it demonstrates |
| --- | --- | --- |
| AI using a computer | `assets/golden/computer-use-story/approved.mp4` | The original approved visual style |
| What happens after you click Pay | `assets/golden/payment-journey/approved.mp4` | Explaining a process through a courier analogy |
| AI recommendation to purchase | `assets/golden/agentic-commerce/approved.mp4` | Turning a product journey into a framework |
| Style overview | `references/approved-contact-sheet.jpg` | A quick visual review of the approved design |

The original HTML projects and their assets are included alongside the reference videos.

## Create a video with an AI assistant

1. Download the full ZIP and give it to an AI assistant that can read files and execute code.
2. Supply a topic, article or infographic.
3. Use this prompt:

> Read SKILL.md and follow the bundled workflow. Create a video about [TOPIC]. Preserve the locked visual style, fonts, colours, scene timing and silent 60-second format. Develop one clear example, run the renderer and quality checks, inspect the output, and deliver the finished MP4.

A text-only chat cannot produce the final MP4 without a code execution environment. No particular AI vendor is required by the bundled Python scripts.

## What is inside the ZIP?

| Item | Purpose |
| --- | --- |
| `SKILL.md` | Instructions for the AI assistant |
| `scripts/build.py` | Builds the video composition from a content-only JSON brief |
| `scripts/render.py` | Checks the composition and exports the MP4 |
| `scripts/test_consistency.py` | Checks asset integrity and repeatable builds |
| `assets/style.css` and bundled fonts | Preserve the approved visual identity |
| `assets/LOCK.json` | Detects changes to the locked assets |
| `assets/example-brief.json` | A working brief to test the workflow |
| `assets/example-output.mp4` | The rendered example for comparison |
| `assets/golden/` | Approved videos and original editable projects |
| `references/` | Story, format, portability and quality guidance |

## Run the supplied example locally

Requirements: Python 3.10+, Node.js 22+, npm/npx, FFmpeg and ffprobe. The renderer uses pinned HyperFrames 0.8.216; first use may need an internet connection to obtain rendering dependencies.

After extracting the ZIP, run these commands from inside `create-consistent-explainer-videos/`:

```bash
python3 scripts/test_consistency.py
python3 scripts/build.py assets/example-brief.json output-project
python3 scripts/render.py output-project --output final.mp4
```

Use a fresh output directory for each run. For a new topic, let the assistant prepare a brief using `references/brief-format.md`; keep the design code unchanged.

## How consistency is checked

- Asset hashes protect the fonts, styles and animation library.
- The builder constrains scene timings, panel types and copy lengths.
- Repeated builds from the same brief are checked for identical HTML and static assets.
- The rendering workflow checks layout and contrast, captures review frames, and verifies duration, dimensions, frame count and absence of audio.
- A person or AI reviewer must still inspect readability, transitions, factual accuracy and storytelling before publishing.

**Consistency means a repeatable design and workflow.** Different AI assistants may write different content. Different browser, operating system or FFmpeg versions can affect the final encoded video. Identical MP4 bytes across every platform are not promised; the approved bundled MP4s provide exact replay of the existing examples.

## For review

Start with the computer-use video, compare the two topic adaptations, then test one new topic. Review whether the explanation is understandable, the text has enough reading time, the reveals are clean and the final takeaway is useful.

The repository currently distributes the complete package as a ZIP. Extract it to access the individual scripts, reference videos and editable projects.
