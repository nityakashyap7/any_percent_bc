# CORL: Behavior Cloning 


## About

This repo contains just a copy of any_percent_bc.py from the CORL team's [repo].(https://github.com/corl-team/CORL/blob/main/algorithms/offline/any_percent_bc.py)


## How to run

### Prerequisites
- Linux (Ubuntu/Debian)
- Python 3.9+
- uv package manager


### Installation

**1. Install MuJoCo (one-time setup):**
```bash
mkdir -p ~/.mujoco && cd ~/.mujoco
wget https://github.com/deepmind/mujoco/releases/download/2.1.0/mujoco210-linux-x86_64.tar.gz
tar -xf mujoco210-linux-x86_64.tar.gz
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:~/.mujoco/mujoco210/bin' >> ~/.bashrc
source ~/.bashrc
```

**2. Install Python dependencies:**
```bash
uv sync
```

**3. Run the file:**
```bash
uv run any_percent_bc.py
```

**don't add `d4rl` to the list of dependencies in `pyproject.toml`!**


[debug chat w claude].(https://claude.ai/share/aad58c93-0eeb-4727-b7a7-ef8370cb46d0)


## Observations about the code
This code uses MSE loss, so it's doing regression. This makes its output actions all deterministic (as opposed to outputting a probability distribution over all actions to sample from, which would provide stochastic behavior). In addition, MSE assumes that the target action policy follows a Gaussian distribution, which inherently limits the expressivity of this model.



