

Nowadays, many people make use of LLMs to learn more about linux, However, This can cause pretty large issues because popular LLMs like chatGPT and claude will hallucinate commands and won't explain what the thing they've provided you with does, they'll also mess up formatting which can be quite dangerous. 

Instead, here's how to use AI safely as part of learning how to use linux:

# setup

for this setup, we'll be using *opencode*, opencode is a CLI application you run from the terminal.

start by installing it using your package manager, for example, for me on arch it's `sudo pacman -Sy opencode`

run opencode once with `opencode`, and set your model to deepseek with the "high" reasoning setting

then close opencode and open opencode.jsonc located in ~/.config/opencode, for example with nano:

`nano ~/.config/opencode/opencode.jsonc`

this should only contain a schema for now, add a permission line, it should look as follows: 
```json
{
  "$schema": "https://opencode.ai/config.json",
  "permission": "ask"
}
```

this will make the LLM always require your explicit permission to prevent it from running un-checked commands. 


# usage

opencode will require explicit permission to even read any information outside of the directory you opened opencode in, this access permission is separate from command permissions. as such, you should *always* use opencode in a specific working directory to the thing you're doing (or an empty workspace).

do not run opencode directly in your ~ (home) directory. 

for "read" functionality, it is totally fine to give "always allow" permissions. this will only apply to the working directory and anything in it by default, as well as any directories you've explicitly allowed access to. 

for anything that runs a command that *can* make modifications to your system, *never* use always allow. 


when opencode offers to run a command, *make sure you understand what the command does*. 

the best way to do this is using the `man` or `tldr` commands, `man` comes built into your OS, `tldr` can be gotten from the tldr or tealdeer packages and updated with `tldr update`

you can run `tldr <command>` or `man <command>` to get an explanation of what the command does.

make sure the command cannot do something destructive, if it can, make sure you understand exactly what the command is doing and to which things. if you're unsure, don't run it. 

do not use the LLM to do complex tasks by itself, use it to figure out how to do simple things you don't know how to do yet, and verify the commands. doing this will allow you to learn the terminal over time as you become familiar with the commands.




