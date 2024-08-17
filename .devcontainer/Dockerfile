FROM debian:bookworm

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
            direnv \
            vim

ARG USERNAME=debian
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME

RUN mkdir -p /home/$USERNAME/.config \
        && echo 'command_timeout = 1000' > /home/$USERNAME/.config/starship.toml

RUN curl -sS https://starship.rs/install.sh | sh -s -- --yes \
        && echo 'eval "$(starship init bash)"' >> /home/$USERNAME/.bashrc

RUN mkdir -p /home/$USERNAME/.config/nixpkgs && echo "{ allowUnfree = true; }" > /home/$USERNAME/.config/nixpkgs/config.nix
