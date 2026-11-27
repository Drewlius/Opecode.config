# $HOME/.config/opencode/ <div align=right>[![wakatime](https://wakatime.com/badge/github/Drewlius/-HOME-.config-opencode-skills-.svg)](https://wakatime.com/badge/github/Drewlius/-HOME-.config-opencode-skills-) <div>
My collection of opencode skills and their corresponding tools. Feel free to take and use any, or all of the uploaded skills and their corresponding tools. If any of them were beneficial to you and worked properly, drop this repo a ★ have fun and happy coding!

## Sane `opencode.jsonc` defaults

> provides some protection against the agent use of  `rm -rf` `git` `gh` and restarting your user session, taking screenshots, etc.

```JSONC
{
  "$schema": "https://opencode.ai/config.json",
  "username": "$USER",
  "default_agent": "plan",
  // your default model to use configure this for local or whichever you prefer
  "model": "local/local",
  "share": "disabled",
  "timezone": "UTC",
  "policies": [
    {
      "action": "integration.use",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "mcp.use",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "skill.use",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "plugin.use",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "websearch.use",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "tool.use",
      "resource": "subagent:*",
      "effect": "allow"
    },
    {
      "action": "tool.use",
      "resource": "shell:*",
      "effect": "allow"
    },
    {
      "action": "tool.use",
      "resource": "shell:rm*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:pip *",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:pipx *",
      "effect": "allow"
    },
    {
      "action": "tool.use",
      "resource": "shell:gh *",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:git pull*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:git checkout*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:git stage*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:git add*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:git commit*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:git push*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:killall plasmashell*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:killall *",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:systemctl --user restart plasma-kwin_wayland.service",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:pkexec --user root systemctl restart plasma-kwin_wayland.service",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:sudo systemctl restart plasma-kwin_wayland.service",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:pkexec --user root systemctl restart plasmalogin.service",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:sudo systemctl restart plasmalogin.service",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:systemctl --user restart plasmalogin.service",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:*queryWindowInfo*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:*getWindowInfo*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "shell:*MoveMouseToFocus*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "read:*/.ssh/*",
      "effect": "deny"
    },
    {
      "action": "tool.use",
      "resource": "read:*/.sshd/*",
      "effect": "deny"
    }
  ],
  "snapshots": true,
  "formatter": true,
  "lsp": true,
  "media": {
    "image": {
      "auto_resize": true,
      "max_width": 3840,
      "max_height": 2160,
      "max_base64_bytes": 9007199254740991
    }
  },
  "tool_output": {
    "max_lines": 1000,
    "max_bytes": 25600
  },
  "permissions": [
    {
      "action": "subagent",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "skill",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "opencode_list_mcp_resources",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "opencode_read_mcp_resources",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "websearch",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "experimental_image_generation",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "external_directory",
      "resource": "*",
      "effect": "ask"
    },
    {
      "action": "external_directory",
      "resource": "/tmp/*",
      "effect": "allow"
    },
    {
      "action": "read",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "read",
      "resource": "*.env",
      "effect": "ask"
    },
    {
      "action": "edit",
      "resource": "*",
      "effect": "ask"
    },
    {
      "action": "edit",
      "resource": "$HOME/repos",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "*",
      "effect": "ask"
    },
    {
      "action": "shell",
      "resource": "glob",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "grep*",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "find",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "gh *",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "git status *",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "git clone *",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "git pull *",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "git diff *",
      "effect": "allow"
    },
    {
      "action": "shell",
      "resource": "git push *",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "git commit *",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "git add *",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "spectacle *",
      "effect": "ask"
    },
    {
      "action": "shell",
      "resource": "gdbus call *queryWindowInfo*",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "gdbus call *getWindowInfo*",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "qdbus * queryWindowInfo",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "qdbus * getWindowInfo",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "busctl call * queryWindowInfo *",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "busctl call * getWindowInfo *",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "systemctl * restart plasma-*",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "systemctl * stop plasma*",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "killall*",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "kill plasmashell",
      "effect": "deny"
    },
    {
      "action": "shell",
      "resource": "killall plasmashell",
      "effect": "deny"
    },
    {
      "action": "todowrite",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "lsp",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "task",
      "resource": "*",
      "effect": "allow"
    },
    {
      "action": "skill",
      "resource": "browser",
      "effect": "allow"
    },
    {
      "action": "browser",
      "resource": "*",
      "effect": "allow"
    }
  ],
  // example mcp server using Opencode's Experiemntal Browser
  "mcp": {
    "servers": {
      "browse": {
        "type": "local",
        "disabled": false,
        "codemode": true,
        "command": [
          "/home/$USER/.local/bin/browse",
          "mcp"
        ],
        "environment": {
          "OPENCODE_BROWSER_RUNTIME": "auto-update"
        },
        "cwd": "/home/$USER",
        "pool": true
      },
    }
  },
  "compaction": {
    "auto": true
  },
  "websearch": {
    "provider": "random"
  },
  "plugins": [],
  // experimental settings change over time. verified for opencode v2.3.2
  "experimental": {
    "todo": true,
    "media_blob": true,
    "image_generate": true,
    "schedules": true,
    "artifacts": true,
    "subagent_depth": 1
  },
  // warming keeps cache alive for approx 30 minutes sending periodic pings invisible to the user to an opened session.
  // true by default
  "warming": true,
  // Locally Hosted Model's Get Configured Here
  "providers": {
    "local--model-server": {
      "settings": {
        "baseURL": "http://127.0.0.1:8080",
        "apiKey": "none"
      },
      // Model Card settings go here else Opencode infers what it can from the local server and omits anything else
      "models": {
        "local-model": { 
          "name": "local",
          "type": "chat"
          "limit": {
            "context": 262144
            "input": 258048
            "output" 32768
      }
    }
  }
}
```
