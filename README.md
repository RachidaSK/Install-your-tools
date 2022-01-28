# Tools and Software installation (MAC)

## VS Code (or IDE of your choice)

1. Navigate to VS code [download page](https://code.visualstudio.com/download) and select Mac as your platform.
2. Open your Downloads folder and click on the file to unzip.
3. Drag the file to your Applications folder.

![VSCode download](https://user-images.githubusercontent.com/40123461/151488316-14947ad9-e894-4d4a-a027-93ec4e81d0eb.png)

You should now be able to access VS code from your Applications folder.

![VSCode usage](https://user-images.githubusercontent.com/40123461/151488494-717fc1f1-2c7b-4066-8b6f-c76eb5da7206.png)

## Terminal

As a programmer, you'll be spending a lot of time in the terminal. If you're not familiar with the terminal, it's an application that allows you to run commands to interact with various applications or processes that don't have a visual user interface.

Since you are on a Mac right now, you already have it. Just follow the steps to open the program.

**Step 1**. Press command + spacebar to open Spotlight Search.

![Spotlight search](https://user-images.githubusercontent.com/40123461/151489020-85d4c763-3080-458f-96f7-3fd670a040e9.png)

**Step 2**.Type **terminal** into the search and then press Enter.

**Note**: You can also find terminal in your applications folder, under Utilities.

![utilities](https://user-images.githubusercontent.com/40123461/151489317-7dbcfe8b-ae21-44e7-9294-7ca4b0716f32.png)

**Step 3**. Keep this window open, you'll need it for the next steps.

![terminal](https://user-images.githubusercontent.com/40123461/151489451-08b9cb85-4c4f-45bf-b05e-5d2194cf467c.png)

**Note**: If you prefer you can download iterm2 [here](https://iterm2.com/downloads.html)

## Xcode

Xcode can be downloaded from the **App store** or you can follow the steps below.

**Step 1**. Run the following line in terminal:

```sh
xcode-select --install
```

**Step 2**.A window will appear with the following message: "The xcode select command requires the command line developer tools. Would you like to install the tools now?" Select "**Install**".

**Step 3**. Agree to the Terms of Service.

Note: If you get a message saying that you don't have permission to run this, copy and paste the following code into your terminal and press Enter.

```sh
sudo xcode-select --install
```

## Homebrew

**Step 1**. Go to [Homebrew](https://brew.sh/). Copy the script listed under Install Homebrew.

![homebrew download](https://user-images.githubusercontent.com/40123461/151490511-5fc1cc60-6075-4bd0-90e2-086f5d5b3ddb.png)

**Step 2**. Paste the script into your Terminal window. Press Enter.

## SSH Keys

To complete these steps, you will need to sign up for a [GitHub](https://github.com/) account if you haven't already, then follow the [instructions](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys) to connect to Github SSH.

## Setting your Git Username for Every Repository on your Computer

![git username](https://user-images.githubusercontent.com/40123461/151491220-6d751145-a357-450d-a11f-786556bfb19b.png)

## Setting Your Git Email for Every Repository on Your Computer

![git email](https://user-images.githubusercontent.com/40123461/151491821-3874039a-6cb8-475b-af16-0aec5cd15890.png)

## NVM

NVM manages multiple Node.js versions. It helps us manage Node versions across our different projects. We will be installing nvm using Homebrew.

**Step 1**. Navigate to this Homebrew page to [install nvm](https://formulae.brew.sh/formula/nvm) and copy the install command.

**Step 2**. Paste the script in your terminal window. Press **Enter**.

**Note**: If you see any error about bash_profile, you might need to install bash or zsh (ohmyzsh).Follow the instructions below to install bash. On Catalina & beyond, **bash** will default to **zsh** for their shell.

**Step 2a**. Navigate to this [page](https://formulae.brew.sh/formula/bash) and copy the install command.

**Step 2b**. Paste the script in your terminal window. Press Enter. Follow the instructions that pops on the terminal screen.

**Note**: If you prefer to use zsh instead, you could install [ohmyzsh](https://ohmyz.sh/#install). The documentation can bee found [here](https://github.com/ohmyzsh/ohmyzsh).

**Step 3**. Add the following to ~/.zshrc or your desired shell configuration file.

```sh
export NVM_DIR="$HOME/.nvm"
[ -s "/usr/local/opt/nvm/nvm.sh" ] && . "/usr/local/opt/nvm/nvm.sh" # This loads nvm
[ -s "/usr/local/opt/nvm/etc/bash_completion.d/nvm" ] && . "/usr/local/opt/nvm/etc/bash_completion.d/nvm" # This loads nvm bash_completion
```

Then **quit** terminal.

**Step 4**. To make nvm automatically change node version in case we have a .nvmrc file in the directory, copy and paste the following in the **~/.zshrc** file. Place this after nvm initialization

```sh
autoload -U add-zsh-hook
load-nvmrc() {
if [[ -f .nvmrc && -r .nvmrc ]]; then
nvm use
elif [[ $(nvm version) != $(nvm version default) ]]; then
echo "Reverting to nvm default version"
nvm use default
fi
}
add-zsh-hook chpwd load-nvmrc
load-nvmrc
```

**Step 5**. Verify that nvm was properly installed by running in a new terminal window.

```sh
nvm --version
```

## Node

As a javascript engineer, your primary development environment will be Node.js. Node is a Javascript engine, and it allows you to build Javascript applications and run them.

1. To install the latest version of node, run:

```sh
nvm install node
```

2. To install a specific version of node (10.16.2 for instance) run:

```sh
nvm install 10.16.2
```

**Note**: You can install as many versions as needed.

3. To use a specific version of node(10.16.2 for instance) for a project run:

```sh
nvm use 10.16.2
```
