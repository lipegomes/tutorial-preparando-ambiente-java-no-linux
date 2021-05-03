# **Preparando ambiente para desenvolver em Java no Linux**

------

Este tutorial foi produzido por mim com intuito de ajudar as pessoas que est iniciando no mundo de desenvolvimento utilizando sistemas operacionais linux.

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

Após digitar o comando acima, aparecerá em seu terminal várias versões do Java e vários pacotes de versões do Java compilados por empresas, copie e cole em seu terminal a versão 11.0.8.hs-adpt da AdoptOpenJDK :

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/sdk-java.png)

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

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/sdk-maven-list.png)

2.2 - Instale a versão mais recente do Maven, após conferir com o comando  **sdk list maven** as versões. Utilize o comando abaixo:

```bash
$ sdk install maven 3.6.3
```

2.3 - Após a instalação do Maven, utilize o comando abaixo para definir a versão do Maven instalada para uso.

```bash```
$ sdk use maven 3.6.3
```

Geralmente o instalador configura a primeira versão instalada do Maven como podemos observar na imagem abaixo:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/maven-install.png)

Após utilizar o comando acima, irá aparecer a confirmação em seu terminal com o número da versão utilizada:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/imagens/sdk-maven-use.png)

2.4 - Verifique a versão do Maven com o comando listado abaixo:

```bash
$ mvn --version
```

Deverá aparecer em seu terminal a seguinte mensagem:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/maven-version.png)

Observe que o comando **mvn --version**, possibilita saber a versão instalada do Maven, além do diretório aonde está instalado o Maven e também a versão do Java, idioma do sistema. Assim como outras informações relevantes sobre o sistema operacional em uso. Lembrando que, o intuito do uso do comando **mvn --version**, é simplesmente saber a versão do Maven e seu diretório de instalação, as demais informações complementam.

------

## 3 - Instalação do IntelliJ IDEA Community utilizando o Jetbrains Toolbox

3.1 - Entre no site abaixo:
https://www.jetbrains.com/idea/

3.2 - Clique em download e baixe o arquivo .tar.gz do Jetbrains Toolbox, em seguida descompacte o arquivo.

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/jetbrains-toolbox.png)

Clique com o botão direito do mouse sobre o arquivo e vá na opção propriedades(em português)/properties(em inglês:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/propriedades.png)

Em seguida vá em permissões e marque a opção de executar esse arquivo como programa:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/executar.png)

Após as etapas acima, clique no arquivo duas vezes para o executar. Assim irá abrir a janela na imagem abaixo:

![](https://github.com/lipegomes/tutorial-preparando-ambiente-java-no-linux/blob/master/imagens/toolbox.png)

Em seguida instale Intellij IDEA Community Edition que é a versão comunitária sendo que a mesma possui certas limitações
se comparada a versão Intellij IDEA Ultimate (versão profissional).

Observe que o Jetbrains Toolbox possibilita a instalação de diversos programas, se sinta livre para instalar o que desejar
sabendo que os programas que contem a palavra community são gratuítos porém com algumas limitações, os que não contém a palavra
community são versões pagas (profissionais). Porém caso seja estudando universitário, há a possíbilidade de soliticar uma licença educacional a Jetbrans no link abaixo:

https://www.jetbrains.com/pt-br/community/education/#students

## 4 - Instalação do IntelliJ IDEA Community utilizando o Snap

4.1 - Para habilitar o snap em seu sistema operacional, entre nos links abaixo e verifique o procedimento no site da snapcraft ou siga os comandos referentes a cada distribuição listadas abaixo:

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

4.2 - Para instalar a versão snap do  IntelliJ IDEA Community, utiliza o comando abaixo:

```bash
$ sudo snap install intellij-idea-community --classic
```

