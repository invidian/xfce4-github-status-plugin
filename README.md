# xfce4 GitHub notifications plugin

This repository offers a script, which reads your GitHub Notifications using GitHub API
and presents them on Xfce panel using [xfce4-genmon-plugin](https://docs.xfce.org/panel-plugins/xfce4-genmon-plugin).

To save some API calls, script uses `xprintidle` to detect if you are idle and sets
idle icon on the panel.

## Screenshots

When you have some unread notications:

![Unread notifications](media/pending.png)

And when there is no notifcations:

![No notifications](media/no-notifications.png)

## Installation

Copy the script to your PATH, for example to `~/.local/bin`:

```sh
mkdir -p ~/.local/bin
cp github-status ~/.local/bin/
```

## Configuration

Status script use [GitHub CLI](https://cli.github.com/) credentials to talk to GitHub API, so follow https://cli.github.com/manual/gh_auth_login to configure it.

Alternatively, you can create the configuration file yourself:

```sh
mkdir -p ~/.config/gh/
cat <<EOF > ~/.config/gh/config.yml
hosts:
    github.com:
        oauth_token: <token>
        user: <username>
EOF
```

## Adding to Panel

Add new `xfce4-genmon-plugin` to your panel and configure it to run the following command:

```sh
.local/bin/github-status
```
