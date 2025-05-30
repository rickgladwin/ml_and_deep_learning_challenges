# ml_and_deep_learning_challenges
challenges for the University of Hull Machine Learning and Deep Learning course

## environments
This repo uses uv for package management and most work is done from within JetBrains' PyCharm IDE.

The most effective way I've found to get uv and PyCharm to play nicely together when running multiple environments is:
- have a uv-managed environment (and its Python interpreter) set up in each subfolder of the repo where the environment needs to be unique
- in PyCharm, open only that subfolder as a project (rather than opening the repo itself as a project)

This will still allow you to use git from the IDE-based command line (git will still detect the `.git` folder in the parent folder of the project), and PyCharm can manage the uv actions and configurations from the project root (which is the subfolder) as it expects.
