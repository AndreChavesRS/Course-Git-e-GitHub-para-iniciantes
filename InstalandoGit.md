**Instalando o Git**
Antes de começar a usar o Git, você tem que torná-lo disponível em seu computador. Mesmo se ele já tiver sido instalado, é provavelmente uma boa idéia atualizar para a versão mais recente. Você pode instalá-lo como um pacote ou através de outro instalador, ou baixar o código fonte e compilá-lo.

**Note**
Este livro foi escrito usando a versão 2.0.0 do Git. Embora a maioria dos comandos usados deve funcionar mesmo em versões antigas do Git, alguns deles podem não funcionar, ou podem agir de forma ligeiramente diferente se você estiver usando uma versão mais antiga. Como o Git é excelente para preservar compatibilidade com versões anteriores, qualquer versão após 2.0 deve funcionar muito bem.

**Instalando no Linux**
Se você deseja instalar o Git no Linux através de um instalador binário, você pode geralmente fazê-lo através da ferramenta básica de gerenciamento de pacotes que vem com sua distribuição. Se você usar Fedora por exemplo, você pode usar o yum:
```bash
$ sudo yum install git-all
```
Se você usar uma distribuição baseada em Debian como o Ubuntu, use o apt-get:
```bash
$ sudo apt-get install git-all
```
Para mais opções de instruções de como instalar o Git em outros vários sistemas Unix, veja na página do Git, em http://git-scm.com/download/linux.

**Instalando no Mac**
Existem várias maneiras de instalar o Git em um Mac. O mais fácil é provavelmente instalar as ferramentas de linha de comando Xcode. No Mavericks (10,9) ou acima, você pode fazer isso simplesmente rodando git a partir do Terminal pela primeira vez. Se você não tiver o Git instalado, ele irá pedir-lhe para instalá-lo.

Se você quiser uma versão mais atualizada, você também pode instalá-lo através de um instalador binário. Um instalador OSX Git é mantido e disponível para download no site do Git, pelo http://git-scm.com/download/mac.

Git OS X installer.
Figure 7. Instalador do Git no OS X.
Você também pode instalá-lo como parte do instalador GitHub para Mac. Sua ferramenta GUI Git tem uma opção para instalar as ferramentas de linha de comando. Você pode baixar essa ferramenta a partir da página GitHub para Mac, em http://mac.github.com.

Instalando no Windows
Há também algumas maneiras de instalar o Git no Windows. A compilação mais oficial está disponível para download no site do Git. Basta ir ao http://git-scm.com/download/win e o download começará automaticamente. Note que este é um projeto chamado Git para Windows (também chamado msysGit), que é algo separado do Git; para mais informações sobre isso, vá para http://msysgit.github.io/.

Para fazer uma instalação automatizada, você pode usar o pacote Git do Chocolatey. Note que o pacote Chocolatey é mantido pela comunidade.

Outra forma fácil de obter Git instalada é através da instalação de GitHub para Windows. O instalador inclui uma versão de linha de comando do Git, bem como a GUI. Ele também funciona bem com o PowerShell, e configura o cache de credenciais sólidas e as devidas configurações CRLF. Vamos saber mais sobre isso um pouco mais tarde, por enquanto basta dizer que estas são coisas que você deveria ter. Você pode baixá-lo da página GitHub para Windows, em http://windows.github.com.

Instalando da Fonte
Algumas pessoas podem achar interessante instalar Git a partir da fonte, para ter a versão mais recente. Os instaladores binários tendem a ficar um pouco atrás, embora após o Git ter amadurecido nos últimos anos, isso faz cada vez menos diferença.

Se você deseja instalar o Git a partir da fonte, você precisa ter as seguintes bibliotecas das quais o Git: curl, zlib, openssl, expat, e libiconv. Por exemplo, se você estiver em um sistema que tem yum (como o Fedora) ou apt-get (tal como um sistema baseado em Debian), você pode usar um destes comandos para instalar as dependências mínimas para compilar e instalar os binários do Git:

source,console]
```bash
$ sudo yum install dh-autoreconf curl-devel expat-devel gettext-devel \
  openssl-devel perl-devel zlib-devel
$ sudo apt-get install dh-autoreconf libcurl4-gnutls-dev libexpat1-dev \
  gettext libz-dev libssl-dev
  ```
Para incluir a documentação em vários formatos (doc, html, info), essas dependências adicionais são necessárias:
```bash
$ sudo yum install asciidoc xmlto docbook2X getopt
$ sudo apt-get install asciidoc xmlto docbook2x getopt 
```
Além disso, se estiver usando o Fedora/RHEL/derivados-do-RHEL, vai precisar executar

```bash 
$ sudo ln -s /usr/bin/db2x_docbook2texi /usr/bin/docbook2x-texi 
```
devido a diferenças nos nomes dos binários.

Quando você tiver todas as dependências necessárias, você poderá baixar o tarball com a última versão de vários lugares. Você pode obtê-lo através da página Kernel.org, em https://www.kernel.org/pub/software/scm/git, ou no espelho no site do GitHub, em https://github.com/git/git/releases. Em geral, é um pouco mais claro qual é a versão mais recente na página do GitHub, mas a página kernel.org também tem assinaturas se você quiser verificar o seu download.

Então, compile e instale:
```bash
$ tar -zxf git-2.0.0.tar.gz
$ cd git-2.0.0
$ make configure
$ ./configure --prefix=/usr
$ make all doc info
$ sudo make install install-doc install-html install-info
```
Depois de ter feito isso, você poderá atualizar o Git através dele mesmo:

```bash 
$ git clone git://git.kernel.org/pub/scm/git/git.git 
```