# Ambiente Linux

### Instalação usando apt-get

Rode esses comandos no seu terminal:

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo sh -c 'wget -qO- https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -'
sudo sh -c 'wget -qO- https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list'
```

### Instalação usando um pacote Debian

Baixe o arquivo .deb direto do site do [dart](https://dart.dev/get-dart) .

### Modifique seu PATH para acessar os bináŕios do Dart

```bash
echo 'export PATH="$PATH:/usr/lib/dart/bin"' >> ~/.profile
```

Ou entao adicione manualmente `export PATH="$PATH:/usr/lib/dart/bin` ao seu `.bashrc` ou ou `.zshrc` .
<p align="center">
  <a href="../00-Introducao/0-Historia.md">
    <img src="/4noobsAssets/anterior.svg" height=35>
  </a>
  <a href="1-AmbienteWindows.md">
    <img src="/4noobsAssets/proximo.svg" height=35>
  </a>
</p>