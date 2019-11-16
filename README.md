# Everything Proxy

More often than not I find myself behind a proxy server. And then, that one tool I need, just doesn't work. Well, this guide might help.

## APT (Debian's Advanced Package Tool)

```bash
# Configure the proxy in the proxy.conf file
cat /etc/apt/apt.conf.d/proxy.conf
Acquire::http::Proxy "http://proxy.domain.com:8080";
```

## Burp Suite

Configure an upstream proxy server:

1. Select tab "User options".
2. Select sub-tab "Connections".
3. Under "Upstream Proxy Servers" add/enable the upstream proxy server to use. Example:
   * Destination host: `*`
   * Proxy host: `proxy.domain.com`
   * Proxy port: `8080`
   * Authentication type: None
4. Click OK

## curl

```bash
# Set the proxy
export HTTP_PROXY=http://proxy.domain.com:8080
export HTTPS_PROXY=http://proxy.domain.com:8080
export ALL_PROXY=http://proxy.domain.com:8080
```

## Firefox

1. Select menu Preferences > Network Settings > Settings...
2. Select on of the following:
   * Auto-detect proxy settings for this network
   * Use system proxy settings
   * Manual proxy configuration

## Git

```bash
# Set the proxy
git config --global http.proxy http://proxy.domain.com:8080

# Check the proxy value
git config --global --get http.proxy

# Unset the proxy
git config --global --unset http.proxy
```

## Homebrew

```bash
# Set the proxy
export HTTP_PROXY=http://proxy.domain.com:8080
export HTTPS_PROXY=http://proxy.domain.com:8080
export ALL_PROXY=http://proxy.domain.com:8080
```

## Hydra

Different types of proxies are possible:

```bash
export HYDRA_PROXY=connect://proxy.domain.com:8080
export HYDRA_PROXY=socks4://proxy.domain.com:8080
export HYDRA_PROXY=socks5://proxy.domain.com:8080
```

## pip (Python's package management)

```bash
export HTTP_PROXY=http://proxy.domain.com:8080
export HTTPS_PROXY=http://proxy.domain.com:8080
```
