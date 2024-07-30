FROM ghcr.io/xtruder/nix-devcontainer:v1
VOLUME /nix

# Install zsh, oh-my-zsh and plugins
ARG ZSH_PLUGINS="git"
RUN for plugin in ${ZSH_PLUGINS}; do plugins="${plugins} -p ${plugin}"; done \
  && sh -c "$(curl -L https://github.com/deluan/zsh-in-docker/releases/download/v1.2.0/zsh-in-docker.sh)" -- \
  $plugins
