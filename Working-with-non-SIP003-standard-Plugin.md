### Important
This manual only applicable on the non-SIP003 standard plugin, if your using plugin is in compliance with the SIP003 standard, read plugin manual or README file to config.

### Supported Versions
4.1.2 and above

### Environment Variables

In Shadowsocks for Windows, you can use 3rd party plugins which does not following the [SIP003](https://github.com/shadowsocks/shadowsocks-org/wiki/Plugin) standard.

Shadowsocks for Windows provided 5 environment variables for [SIP003] plugin config:

`%SS_LOCAL_HOST%`
`%SS_LOCAL_PORT%`
`%SS_REMOTE_HOST%`
`%SS_REMOTE_PORT%`
`%SS_PLUGIN_OPTIONS%` (optional)

These environment variables will inform plugin how to config both local(your machine) and remote(server) endpoints.

### QuickStart
1. Prepare a plugin program to Shadowsocks.exe directory or somewhere you must know, for example: 
```
D:\Shadowsocks\plugin_windows_amd64.exe
```

Read plugin manual, find out how to use the parameter to config plugin and how to assign server host, server port, localhost and local port.

2. Open Shadowsocks for Windows "Edit Servers" window, Add server as usual.

3. In Server Port field, write plugin listening port from server.

4. In Plugin Program field, write the plugin path (absolute or relative), for example: 
```
D:\Shadowsocks\plugin_windows_amd64.exe
```
or
```
plugin_windows_amd64.exe
```

5. In Plugin Options field, we could keep it blank.

6. In Plugin Arguments field, in this case, the plugin is [kcptun](https://github.com/xtaci/kcptun). It uses `-l` parameter to assign `local:port`, `-r` parameter to assign `server:port`. We could compose the command as following:
```
-l %SS_LOCAL_HOST%:%SS_LOCAL_PORT% -r %SS_REMOTE_HOST%:%SS_REMOTE_PORT% --key <Plugin Password> --crypt <Encryption algorithm> --mode <Selected mode>
```
You need to fill the <Plugin Password>, <Encryption algorithm> and <Selected mode> by yourself.

7. Done.

### Troubleshooting
1. Confirm the plugin program executable file exists and the path is correct.

2. Determine whether the plugin program is executed or not by using Task Manager.

3. Check the plugin parameters. Is there any mistakes such as typo or missing parameters or mismatch with server configuration.
