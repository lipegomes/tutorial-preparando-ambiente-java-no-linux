# **Preparando ambiente para desenvolver em Java no Linux**

------

## 1 - Instalação do sdkman

1.1 -  Entre no site abaixo:
https://sdkman.io/ 

1.2 -  Cole o comando abaixo no terminal para instalar o sdkman, tecle enter e espere concluir a instalação, apos isso reinicie o terminal:

```bash
$ curl -s "https://get.sdkman.io" | bash 
```

1.3 - Digite o comando abaixo para verificar as versões de java disponível nos repositórios do sdkman:

```bash
$ sdk list java | less
```

Após digitar o comando acima, aparecerá em seu terminal várias versões do Java e vários pacotes de versões do Java compilados por empresas, copie e cole em seu terminal a versão 11.0.8.hs-adpt da  AdoptOpenJDK :

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/sdk-java.png)

1.4 - Instale a versão 11 AdoptOpenJDK do Java com o comando abaixo:

```bash
$ sdk install java 11.0.8.hs-adpt
```

1.5 - Após instalação da versão 11 do Java, verifique a versão instalada com o comando abaixo:

```bash
$ java --version
```

1.6 - Conforme a versão do Java 11 instalada, deverá aparecer as seguintes informações abaixo:

```
openjdk 11.0.8 2020-07-14
OpenJDK Runtime Environment AdoptOpenJDK (build 11.0.8+10)
OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11.0.8+10, mixed mode)
```

------

## 2 - Instalação Maven

2.1 - Digite o comando abaixo no terminal para listar as versões do Maven disponíveis nos repositórios:

```bash
$ sdk list maven
```

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/sdk-maven-list.png)

2.2 - Instale a versão mais recente do Maven, após conferir com o comando  **sdk list maven** as versões. Utilize o comando abaixo:

```bash
$ sdk install maven 3.6.3
```

2.3 - Após a instalação do Maven, utilize o comando abaixo para definir a versão do Maven instalada para uso.
Geralmente o instalador configura a primeira versão instalada do Maven como  podemos observar na imagem abaixo:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/maven-install.png)

Porém, por motivo de aprendizado, utilize o comando abaixo para definir a versão do Maven instalada ou para versões diferentes se desejar utilizar mais de uma versão:

```bash
$ sdk use maven 3.6.3
```

Após utilizar o comando acima, irá aparecer a confirmação em seu terminal com o número da versão utilizada:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/sdk-maven-use.png)

2.4 - Verifique a versão do Maven com o comando listado abaixo:

```bash
$ mvn --version
```

Deverá aparecer em seu terminal a seguinte mensagem:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/maven-version.png)

Observe que o comando **mvn --version**, possibilita saber a versão instalada do Maven, além do diretório aonde está instalado o Maven e também a versão do Java, idioma do sistema. Assim como outras informações relevantes sobre o sistema operacional em uso. Lembrando que, o intuito do uso do comando **mvn --version**, é simplesmente saber a versão do Maven e seu diretório de instalação, as demais informações complementam.

------

## 3 - Instalação do IntelliJ IDEA Community

3.1 - Entre no site abaixo:
https://www.jetbrains.com/idea/

3.2 - Clique em download e instale a versão do IntelliJ IDEA Community referente a sua distribuição linux. Porém para facilitar, estarei utilizando a versão de empacotamento snap que pode ser utilizada na grande maioira das distribuições linux. Para habilitar o snap em seu sistema operacional, entre nos links abaixo e verifique o procedimento no site da snapcraft ou siga os comandos referentes a cada distribuição listadas abaixo:

**Lembrando que caso a sua distribuição não esteja listada nesse tutorial, você deve procurar em https://snapcraft.io a forma de instalar o snapd em sua distribuição linux.**

**Ubuntu**:
https://snapcraft.io/docs/installing-snap-on-ubuntu

```bash
$ sudo apt update
$ sudo apt install snapd
```

**Fedora**:
https://snapcraft.io/docs/installing-snap-on-fedora

```bash
$ sudo dnf update
$ sudo dnf install snapd
```

Após instalar o snapd no fedora, reinicie o sistema operacional e digite o comando abaixo para criar um link simbólico entre **/var/lib/snapd/snap** e o **/snap**:

```bash
$ sudo ln -s /var/lib/snapd/snap /snap
```

**Manjaro**:
https://snapcraft.io/docs/installing-snap-on-manjaro-linux
```bash
$ sudo pacman -S snapd
```

Após instalar o snapd no manjaro, habilite o socket do snapd:

```bash
$ sudo systemctl enable --now snapd.socket
```

3.3 - Para instalar a versão snap do  IntelliJ IDEA Community, utiliza o comando abaixo:

```bash
$ sudo snap install intellij-idea-community --classic
```

