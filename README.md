# rthebachelor-mods-discord-notify
Discord bot to remind us to update the megathread hub

# Requirements

I used the [discord.py API](https://github.com/discord/discord-api-docs) to build a simple bot that will notify certain users or roles at a set interval to update the megathread hub. I attempted to write this bot in a way that can be generalized to notification at some set interval for other tasks in the future.

## Environment Creation

This project is built using the Python programming langauge distributed through [Anaconda](https://www.anaconda.com/). The following code will provide the steps to build, activate and control the development environment for this bot.

We will first remove any conda virtual environments of the name `rthebachelor-mods-discord-notify` to ensure that the environment is our only source of truth.

```bash
conda remove --name rthebachelor-mods-discord-notify --all
```

We will now activate the environment as follows:

```bash
conda env create -f environment.yml
conda activate rthebachelor-mods-discord-notify
```

To stop using the environment run the following command:

```bash
conda deactivate
```

## Notebook Configuration

The environment has packages necessary to debug in a jupyter notebook environment. To create the kernel to accompany the notebook run the following commands:

```bash
conda activate rthebachelor-mods-discord-notify
python -m ipykernel --install --user --name rthebachelor-mods-discord-notify --display-name "Python3.9 (rthebachelor-mods-discord-notify)"
```

After the virtual environment is activated we install an ipykernel of the current environment under the name "Python3.9 (rthebachelor-mods-discord-notify)". When running a jupyter notebook **do not** use the vscode client. Please use the CLI `jupyter-notebook` command.

## Modifications

If you make __any__ modifications to the environment and wish to store the changes in the `environment.yml` file plese follow the directions below.

To install a package to the environment run the following command:

```bash
conda install --name rthebachelor-mods-discord-notify <PACKAGE-NAME>
```

If you wish to update the `environment.yml` file you must ensure that the prefix is user-agnostic. In a standard `environment.yml` configuration the `prefix` field informs the system of the destination of the environment on disk. As we will be utilizing a reproducible workflow we should not need this field. 

```bash
conda activate rthebachelor-mods-discord-notify ## ensure the env is active to export
conda env export | grep -v "^prefix: " > environment.yml
```
