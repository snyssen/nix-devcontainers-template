FROM ghcr.io/xtruder/nix-devcontainer@sha256:b4e4049d00c55bb9663cb6ef446b9a0615ad0e8d64a1876372fd773ee7b9ecac
VOLUME /nix

# Install zsh, oh-my-zsh and plugins
ARG ZSH_PLUGINS
ENV ZSH_PLUGINS_FORCED="git zsh-autosuggestions zsh-syntax-highlighting"
RUN for plugin in ${ZSH_PLUGINS_FORCED}; do plugins="${plugins} -p ${plugin}"; done \
  && for plugin in ${ZSH_PLUGINS}; do plugins="${plugins} -p ${plugin}"; done \
  && sh -c "$(curl -L https://github.com/deluan/zsh-in-docker/releases/download/v1.2.0/zsh-in-docker.sh)" -- \
  $plugins \
  && git clone https://github.com/zsh-users/zsh-autosuggestions.git $HOME/.oh-my-zsh/custom/plugins/zsh-autosuggestions \
  && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $HOME/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
