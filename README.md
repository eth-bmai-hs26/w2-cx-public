# Weekend 2 coding exercises, public material

CAS "Building ML/AI Applications" (BMAI), ETH Zurich, HS26. Weekend 2.

This repository holds the participant-facing notebooks for weekend 2. It is
public so that every notebook opens in Google Colab with one click. The
solutions and the grading material live in `w2-cx-private`.

The course website links to everything here:

    https://eth-bmai-hs26.github.io/BMAI-PAGE/

## Exercises

| Slot | Exercise | Open |
|---|---|---|
| TBA | **Fridge Chef** | [Open in Colab](https://colab.research.google.com/github/eth-bmai-hs26/w2-cx-public/blob/main/fridge-chef/fridge_chef.ipynb) |

More weekend 2 exercises are added here as they are finished.

## Fridge Chef

`fridge-chef/fridge_chef.ipynb` builds a kitchen assistant twice: first out of
plain `if/else`, then out of an LLM that picks the next tool to call. The two
share the same six tools and the same loop, so the difference between them is
exactly the part a model buys you. The notebook then points the same loop at a
small model running on the Colab GPU, and closes with a five-request
evaluation, because one good demo proves nothing.

Six sections: the rule-based agent, the LLM agent, the two side by side,
swapping the cloud model for a local one, evaluating on a fixed suite, and a
free-form section to try your own requests. Four `TODO`s, about an hour. Each
TODO is marked 🎯 in the code and has hints in the cell above it.

Prerequisites are Python basics, meaning functions, loops and dictionaries.
No prior experience with LLM APIs is assumed; the notebook explains function
calling as it goes.

Everything the simulation needs is defined inside the notebook, so there is
nothing to clone. The only dependency installed is `openai`. Sections 2 to 6
need a model, and the notebook offers two ways to get one:

- **Cloud (default):** an [OpenRouter](https://openrouter.ai) API key, stored
  in Colab under *Secrets* as `OPENROUTER_API_KEY`. The free tier is enough for
  the exercise, with one caveat: the evaluation in section 5 makes about 40
  requests in one go, which is most of a free key's daily allowance.
- **Local:** set `BACKEND = "local"` in the *Connect a model* cell and the
  notebook installs Ollama and downloads a 4B-parameter model onto the Colab
  T4 GPU. No key, no quota, and a good look at how a small model behaves.

To run it on your own machine instead, any Jupyter with Python 3.10 or newer
works; `pip install openai` is the only setup.
