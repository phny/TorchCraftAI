# TorchCraftAI - paper open source release

TorchCraftAI is a platform that lets you build agents to play (and learn to play) *StarCraft®: Brood War®*†. TorchCraftAI includes:
- A modular framework for building StarCraft agents
- CherryPi, a bot which plays complete games of StarCraft (1st place SSCAIT 2017-18)
- A reinforcement learning environment with minigames, models, and training loops
- TorchCraft support for TCP communication with StarCraft and BWAPI
- Support for Linux, Windows, and OSX

This branch contains the experimental code for the paper "A Structured Prediction Approach for Generalization in Cooperative Multi-Agent Reinforcement Learning" (Neurips 2019) by N.Carion, G.Synnaeve, A.Lazaric, N.Usunier. A version of the paper is available on [arxiv](https://arxiv.org/abs/1910.08809)

To reproduce the results, first follow the general instructions for building as found below. Then you can build the targeting experiment code 
```bash
cd build && make targeting && cd ..
```

Then you can simply start a training. For example the scenario "w15v17" with the same hyper-parameter as the paper, is trained as follows:
```bash
./build/targeting/targeting   --minloglevel 0   -v -1  --scenario wraith --seed 42 --model_type quad_dm  --dump_replay --use_pairwise_feats --difficulty 0 --normalize_dist --lr 2.8e-5 --policy_ratio 2.5e2 --returns_length 6 --correlated_steps 7 --optim "adam" --batch_size 32 --num_workers 64 --scenario_size 15
```

Refer to the appendix of the paper for the hyper-parameters used.

## Get started

See guides for:

- [Linux](https://torchcraft.github.io/TorchCraftAI/docs/install-linux.html)
- [Windows](https://torchcraft.github.io/TorchCraftAI/docs/install-windows.html)
- [OSX](https://torchcraft.github.io/TorchCraftAI/docs/install-macos.html)

## Documentation

* [Home](https://torchcraft.github.io/TorchCraftAI)
* [Architecture overview](https://torchcraft.github.io/TorchCraftAI/docs/architecture.html)
* [Code reference](https://torchcraft.github.io/TorchCraftAI/reference/)

### Tutorials

* [Train a model to place buildings](https://torchcraft.github.io/TorchCraftAI/docs/bptut-intro.html)
* [Train a model to fight](https://torchcraft.github.io/TorchCraftAI/docs/microtut-intro.html)

## Licensing

We encourage you to experiment with TorchCraftAI! See [LICENSE](https://github.com/TorchCraft/TorchCraftAI/blob/master/LICENSE), plus more on [contributing](https://github.com/TorchCraft/TorchCraftAI/blob/master/CONTRIBUTING.md) and our [code of conduct](https://github.com/TorchCraft/TorchCraftAI/blob/master/CODE_OF_CONDUCT.md).

†: StarCraft is a trademark or registered trademark of Blizzard Entertainment, Inc., in the U.S. and/or other countries.  Nothing in this repository should be construed as approval, endorsement, or sponsorship by Blizzard Entertainment, Inc.
