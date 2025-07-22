# Baseline Connectivity Test Results

This document captures the baseline connectivity state when the system is working properly. Use this as reference when troubleshooting connectivity issues.

## Date: 2025-01-22

## Network Connectivity Tests

### nslookup github.com
```
Server:  dev.opt
Address:  192.168.100.1

Non-authoritative answer:
Name:    github.com
Address:  140.82.121.4
```

### ping github.com
```
Pinging github.com [140.82.121.4] with 32 bytes of data:
Reply from 140.82.121.4: bytes=32 time=51ms TTL=47
Reply from 140.82.121.4: bytes=32 time=49ms TTL=47
Reply from 140.82.121.4: bytes=32 time=49ms TTL=47
Reply from 140.82.121.4: bytes=32 time=54ms TTL=47

Ping statistics for 140.82.121.4:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 49ms, Maximum = 54ms, Average = 50ms
```

### Test-NetConnection github.com -Port 443
```
ComputerName     : github.com
RemoteAddress    : 140.82.121.4
RemotePort       : 443
InterfaceAlias   : Wi-Fi
SourceAddress    : 192.168.100.10
TcpTestSucceeded : True
```

## Git Configuration

### git remote -v
```
origin	https://github.com/zaki982/Deep-Learning-using-Keras (fetch)
origin	https://github.com/zaki982/Deep-Learning-using-Keras (push)
```

### git config --list (proxy/http/credential related)
```
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/etc/ssl/certs/ca-bundle.crt
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
remote.origin.url=https://github.com/zaki982/Deep-Learning-using-Keras
lfs.https://github.com/zaki982/Deep-Learning-using-Keras.git/info/lfs.access=basic
```

## Summary

- DNS resolution: Working (github.com resolves to 140.82.121.4)
- ICMP connectivity: Working (4/4 packets successful, ~50ms average)
- HTTPS connectivity: Working (port 443 connection successful)
- Git remotes: Configured for HTTPS access to GitHub
- Git credentials: Using credential manager with SSL backend
