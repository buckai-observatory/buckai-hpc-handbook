# BuckAI HPC Handbook

Practical notes from the BuckAI Observatory on using OSU's Unity HPC cluster — SSH, AI coding assistants (Claude Code, Copilot, Gemini), mamba, tmux, Jupyter, and the workflows that make them all play nicely together.

Built at the [BuckAI Observatory](https://buckai-observatory.org) at Ohio State University.

## What this is

A practical, opinionated **reference handbook** for using OSU's Unity HPC cluster — written for BuckAI Observatory students, postdocs, and collaborators, but useful for anyone at OSU getting started on HPC.

It takes you from *"I just got my HPC account and the SSH prompt is rejecting me"* to *"I'm training models on GPU nodes from VS Code on my laptop, with my AI coding assistant helping me debug, while sharing a reproducible mamba environment with my labmates."*

The handbook is **opinionated** about workflows that work well in practice, and explicitly warns about the ones that look fine but break in subtle ways (mixing pip with conda, over-allocating Slurm resources, `nohup`-ing things that needed `tmux`, etc.).

## Live site

📖 **Rendered handbook:** <http://buckai-observatory.org/buckai-hpc-handbook/>

🎓 **Companion self-guided practicum:** <https://github.com/buckai-observatory/buckai-hpc-course>

The practicum turns the chapters of this handbook into a 1-credit, 15-week course with weekly labs and a capstone project.

## What's covered

| Section | Topics |
|---|---|
| **SSH** | SSH config + connection multiplexing through the ASC jumphost · SSH keys concepts and best practices · VS Code Remote-SSH + AI coding assistants (Claude Code, GitHub Copilot, Gemini Code Assist) |
| **HPC fundamentals** | `.bashrc`, aliases, `PATH`, `umask 002`, Unix groups and Slurm partitions · `tmux` and `nohup` for persistent sessions, plus the `livenode` pattern · Jupyter on the cluster (OnDemand + SSH-tunnel) · mamba environments and the pip-conda trap |
| **Slurm** | Basics: `sbatch`, `squeue`, monitoring, common directives · **Best practices**: right-sizing memory/CPU/walltime, measuring with `seff` and `/usr/bin/time -v`, the diagnostic wrapper · CPU job templates: single-thread, threaded, joblib, arrays, MPI · GPU job templates: single GPU, DDP, hyperparameter sweeps |

## How the site is built

This is a [Quarto](https://quarto.org) website. To preview locally:

```bash
git clone https://github.com/buckai-observatory/buckai-hpc-handbook.git
cd buckai-hpc-handbook
quarto preview                  # serves at http://localhost:nnnn
```

To render the static site to `docs/`:

```bash
quarto render
```

The `docs/` folder is committed to the repo and served via GitHub Pages with a custom domain at `buckai-observatory.org/buckai-hpc-handbook/`.

Source files are `.qmd` (Quarto markdown). Most prose lives under `ssh/`, `hpc/`, and `slurm/` directories matching the three sidebar sections.

## Audience

- **Primary:** BuckAI Observatory students, postdocs, and collaborators using OSU's Unity HPC cluster.
- **Also useful for:** anyone at OSU (CAS or elsewhere) getting started on Unity or OSC, and HPC users at other institutions whose workflow is similar (SSH through a jumphost with MFA, Slurm, mamba environments, etc.).

No prior HPC experience is assumed, but comfort with Python and a Unix terminal is.

## License and contributions

This handbook is **open educational content** — designed to be read, forked, and adapted. We welcome:

- 🐛 Bug reports and corrections (open an issue)
- 📝 Pull requests with clearer explanations, missing topics, or new pages
- 🍴 Forks for adapting to other clusters / institutions

For OSU students: this is also what the [BuckAI HPC Practicum](https://github.com/buckai-observatory/buckai-hpc-course) uses as its reading material, so improvements here flow to that course too.

## Acknowledgments

- The Unity HPC team at OSU's ASC for keeping the cluster running.
- Anthropic (Claude), Microsoft/GitHub (Copilot), and Google (Gemini) for AI coding assistants that make this kind of practical learning dramatically more accessible.
- Generations of BuckAI students who hit every one of these issues so future readers don't have to.
