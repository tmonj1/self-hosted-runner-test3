# self-hosted-runner-test

## How to run a self-hosted runner.

### Generate an access token

1. go to `Settings / Developer settings / Personal access tokens` on your GitHub page.
1. click `Generate new access token` button.
1. enter token name in `Note` field, check `repo` and `workflow` in `Select scope`.
1. click `Generate token` button.

Take a note of the generated token on the screen.

### Run a self-hosted runner

The description below is applicable to Linux and Mac OSX only, not to Windows. 

1. `git clone git@github.com:tmonj1/self-hosted-runner-test3.git`
1. cd self-hosted-runner-test3
1. set GITHUB_ACTIONS_PAT environment variable to {{PAT}}} with `export GITHUB_ACTIONS_PATH={{PAT}}`
1. run `docker-compose up --build -d`

### Confirm

1 run `docker logs ghr`.

If you see the following banner and messages, it's OK.

```
Runner reusage is disabled
Obtaining the token of the runner
Configuring

--------------------------------------------------------------------------------
|        ____ _ _   _   _       _          _        _   _                      |
|       / ___(_) |_| | | |_   _| |__      / \   ___| |_(_) ___  _ __  ___      |
|      | |  _| | __| |_| | | | | '_ \    / _ \ / __| __| |/ _ \| '_ \/ __|     |
|      | |_| | | |_|  _  | |_| | |_) |  / ___ \ (__| |_| | (_) | | | \__ \     |
|       \____|_|\__|_| |_|\__,_|_.__/  /_/   \_\___|\__|_|\___/|_| |_|___/     |
|                                                                              |
|                       Self-hosted runner registration                        |
|                                                                              |
--------------------------------------------------------------------------------

# Authentication


√ Connected to GitHub

# Runner Registration




√ Runner successfully added
√ Runner connection is good

# Runner settings


√ Settings Saved.


√ Connected to GitHub

Current runner version: '2.294.0'
2022-07-26 12:30:22Z: Listening for Jobs
```

## Todo's

install GH on self-hosted runner

```
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/etc/apt/trusted.gpg.d/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/trusted.gpg.d/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh
```

Require Review approval





