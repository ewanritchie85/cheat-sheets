# systemd Cheat Sheet

## Service Management

| Action                    | Command                                          |
|---------------------------|--------------------------------------------------|
| Start a service           | `sudo systemctl start <service>`                 |
| Stop a service            | `sudo systemctl stop <service>`                  |
| Restart a service         | `sudo systemctl restart <service>`               |
| Reload config (no restart)| `sudo systemctl reload <service>`                |
| Show status               | `systemctl status <service>`                     |
| Enable at boot            | `sudo systemctl enable <service>`                |
| Disable at boot           | `sudo systemctl disable <service>`               |
| Check if enabled          | `systemctl is-enabled <service>`                 |
| Show recent logs          | `journalctl -u <service>`                        |
| Show & follow logs        | `journalctl -u <service> -f`                     |
| Show logs (since today)   | `journalctl -u <service> --since today`          |

## System Management

| Action               | Command                                     |
|----------------------|---------------------------------------------|
| List all units       | `systemctl list-units`                      |
| List failed units    | `systemctl --failed`                        |
| List all services    | `systemctl list-units --type=service`       |
| Reload systemd       | `sudo systemctl daemon-reload`              |
| Reboot system        | `sudo systemctl reboot`                     |
| Poweroff system      | `sudo systemctl poweroff`                   |

## Service File Locations

- **System services:** `/etc/systemd/system/` or `/lib/systemd/system/`
- **User services:** `~/.config/systemd/user/`

## Common Usage Examples

- **Start Nginx:**  
  `sudo systemctl start nginx`

- **Show status of sshd:**  
  `systemctl status ssh`

- **View real-time logs for Jenkins:**  
  `journalctl -u jenkins -f`

- **Enable your custom service:**  
  `sudo systemctl enable myscript.service`

## Create/Edit a Service

1. **Create a file:** `/etc/systemd/system/myapp.service`
2. **Example content:**
    ```ini
    [Unit]
    Description=My App

    [Service]
    ExecStart=/usr/bin/python3 /path/to/app.py
    Restart=always

    [Install]
    WantedBy=multi-user.target
    ```
3. **Reload and enable:**
    ```bash
    sudo systemctl daemon-reload
    sudo systemctl enable myapp
    sudo systemctl start myapp
    ```