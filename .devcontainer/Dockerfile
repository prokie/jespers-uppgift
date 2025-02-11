FROM ubuntu:latest

# Install dependencies
RUN apt update && apt install -y curl git zsh wget fonts-powerline zsh-autosuggestions zsh-syntax-highlighting

# Install Oh My Zsh (unattended)
RUN sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" --unattended \
    && chsh -s $(which zsh)

# Install zsh plugins
RUN git clone https://github.com/zsh-users/zsh-autosuggestions                   ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
RUN git clone https://github.com/zsh-users/zsh-syntax-highlighting.git           ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
RUN git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git  ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
RUN git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autocomplete

# Modify .zshrc to use the desired plugins
RUN sed -i 's/^plugins=(git)$/plugins=(git zsh-autosuggestions zsh-syntax-highlighting fast-syntax-highlighting zsh-autocomplete)/' ~/.zshrc


RUN curl -LsSf https://astral.sh/uv/install.sh | sh

# Set default shell to Zsh
CMD ["zsh"]