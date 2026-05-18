\# Linux Commands Cheat Sheet



\## Process Management Commands



| Command | Usage |

|---|---|

| ps -ef | View all running processes |

| top | Monitor CPU and memory usage |

| htop | Interactive process monitoring |

| kill -9 PID | Force stop a process |

| pkill process-name | Kill process using name |

| pgrep process-name | Find process ID |

| nice -n 10 command | Start process with priority |

| renice PID | Change running process priority |

| jobs | Show background jobs |

| free -h | Check memory usage |



\---



\## File System Commands



| Command | Usage |

|---|---|

| ls -ltr | List files with details |

| cd directory | Change directory |

| pwd | Show current path |

| mkdir folder-name | Create new directory |

| rm -rf folder | Remove files/directories |

| cp source destination | Copy files |

| mv source destination | Move or rename files |

| find / -name file | Search files |

| du -sh \* | Check directory sizes |

| df -h | Check disk usage |

| chmod 755 file | Change file permissions |

| chown user:user file | Change ownership |

| tail -f logfile | Monitor logs live |

| grep keyword file | Search text in files |

| vi filename | Edit files |



\---



\## Networking \& Troubleshooting Commands



| Command | Usage |

|---|---|

| ping google.com | Check connectivity |

| ip addr | View IP configuration |

| netstat -tulnp | Check listening ports |

| ss -tulnp | View active connections |

| curl URL | Test API or URL response |

| dig domain.com | DNS lookup |

| traceroute google.com | Trace network path |

| nslookup domain.com | Query DNS information |

| telnet host port | Test port connectivity |

| wget URL | Download files |



\---



\## System \& Service Commands



| Command | Usage |

|---|---|

| systemctl status service | Check service status |

| systemctl restart service | Restart service |

| systemctl enable service | Enable service on boot |

| journalctl -xe | View detailed system logs |

| uname -a | Show system information |

| uptime | Check system uptime |

| whoami | Current logged-in user |

| hostnamectl | Show hostname details |



\---



\## Key Learning



Strong Linux command-line skills help in faster troubleshooting, monitoring, log analysis, and production issue resolution in DevOps environments.

