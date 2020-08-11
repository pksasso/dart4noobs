# 2- Ambiente

# 2.1- Ambiente Linux

### Instalação usando apt-get

Rode esses comandos no seu terminal:

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo sh -c 'wget -qO- https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -'
sudo sh -c 'wget -qO- https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list'
```

### Instalação usando um pacote Debian

Baixe o arquivo .deb aqui [https://storage.googleapis.com/dart-archive/channels/stable/release/latest/linux_packages/dart_2.9.0-1_amd64.deb](https://storage.googleapis.com/dart-archive/channels/stable/release/latest/linux_packages/dart_2.9.0-1_amd64.deb) .

### Modifique seu  PATH para acessar os bináŕios do Dart

 

```bash
echo 'export PATH="$PATH:/usr/lib/dart/bin"' >> ~/.profile
```

Ou entao adicione manualmente `export PATH="$PATH:/usr/lib/dart/bin` ao seu `.bashrc` ou ou `.zshrc` .

# 2.2- Ambiente Windows

### Instalação usando Chocolatey

```powershell
choco install dart-sdk
```

### Atualização quando tiver nova versão

```powershell
choco upgrade dart-sdk
```

# 2.3- Ambiente macOS

### Instalação usando homebrew

```bash
brew tap dart-lang/dart
brew install dart
```

### Atualização quando tiver nova versão

```bash
brew upgrade dart
```

# 2.4- Editores

Para fins de estudo é possivel usar o Dartpad, uma IDE online de dart provida pelo Google.

Caso queria desenvolver na sua máquina os editores mais famosos como Visual Studio Code, IntelliJ e Android Studio tem extensões para dart, assim como Vim, Emacs, Atom, Eclipse entre outros.