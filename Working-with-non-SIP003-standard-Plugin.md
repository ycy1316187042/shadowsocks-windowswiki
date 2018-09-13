### Important
This manual only applicable on the non-SIP003 standard plugin, if your using plugin is in compliance with the SIP003 standard, read plugin manual or README file to config.

### Environment Variables

In Shadowsocks for Windows, can use 3rd plugins without [SIP003](https://github.com/shadowsocks/shadowsocks-org/wiki/Plugin) standard support.

Shadowsocks for Windows provided 4 environment variables for plugin config:

`%SS_LOCAL_HOST%` `%SS_LOCAL_PORT%` `%SS_REMOTE_HOST%` `%SS_REMOTE_PORT%`

These environment variables will inform plugin how to config localhost address, local port number, remote host address, and remote port number.

### QuickStart
Download plugin to Shadowsocks.exe directory or somewhere you must know, for example: 
```
D:\Shadowsocks\client_windows_amd64.exe
```

Read plugin manual, find out how to use the parameter to config plugin and how to assign server host, server port, localhost and local port.

In most case, you can use `-h` parameter in the command line (cmd.exe) to get this information:
```
client_windows_amd64.exe -h
```

Open Shadowsocks for Windows "Edit Servers" window, Add server as usual.

In Server Port, write plugin port on server.

In Plugin Program, write the plugin path, for example: 
```
D:\Shadowsocks\client_windows_amd64.exe
```

In Plugin Options, keep it blank.

In Plugin Arguments, for example, The plugin is [kcptun](https://github.com/xtaci/kcptun), The kcptun using `-l` parameter to assign `local:port`, `-r` parameter to assign `server:port`, Then:
```
-l %SS_LOCAL_HOST%:%SS_LOCAL_PORT% -r %SS_REMOTE_HOST%:%SS_REMOTE_PORT% --key <Plugin Password> --crypt <Encryption algorithm> --mode <Selected mode>
```

When everything is done, just click the OK button, and should be work.

### Troubleshooting
If not working, open Task Manager, go to Progress tab(or details tab), check progress list, is plugin program file name in the list? 

If not, maybe is some wrong in the plugin parameter, usually is the spelling mistake or too many arguments.

If it's in Progress list, maybe is parameter variate is wrong, usually is password is not correct, encryption algorithm or mode not matching, check settings with server-side config.
