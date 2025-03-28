# Kubernetes Auto-Suggestions and Auto-Completion

## Enable kubectl Autocompletion for the Current Session
```bash
source <(kubectl completion bash)
```

## Make Autocompletion Persistent

### For Bash Users
```bash
echo 'source <(kubectl completion bash)' >> ~/.bashrc
source ~/.bashrc
```

### For Zsh Users
```bash
echo 'source <(kubectl completion zsh)' >> ~/.zshrc
source ~/.zshrc
```

## Install bash-completion (If Needed)
If autocompletion is not working, install `bash-completion`:
```bash
sudo apt update
sudo apt install bash-completion -y
echo 'source /usr/share/bash-completion/bash_completion' >> ~/.bashrc
source ~/.bashrc
```

## Verify the Setup
Type `kubectl` and press **Tab** twice to check if suggestions appear.

---

Now, `kubectl` auto-suggestions and auto-completion are enabled on your Ubuntu machine! 🚀
