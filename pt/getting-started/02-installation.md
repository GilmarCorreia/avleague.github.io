---
layout: single
title: "Instalação"

permalink: /pt/primeiros-passos/instalacao/

sidebar:
    nav: "primeiros-passos"
    
toc: true
toc_label: "Conteúdo"
toc_icon: "cog"
---

Para executar a aplicação serão necessários a instalação do **Anaconda** e dos pacotes liberados nos *releases* da página do GitHub da AVL. Recomendamos também a instalação do **7-Zip** para extrair os arquivos do simulador e do **Git-Bash** para trabalhar com controle de versionamento de arquivos.

 - Baixar o [Anaconda](https://www.anaconda.com/products/individual) de acordo com os requisitos de sua máquina.
 - Baixar o [7-Zip](https://www.7-zip.org/download.html).
 - Baixar o [Git-Bash](https://gitforwindows.org/).
 - Baixar o [*release*](https://github.com/SIR-research/AVL/releases) mais recente do simulador. 

O *release* do simulador busca ser o mais completo e estável possível, assim recomendamos que realize o *download* do mesmo. Nesse arquivo encontrará:
 - Os arquivos do simulador (API).
 - Os ambientes de simulação recomendados.

Os procedimentos a seguir serão específicos para configurar a execução do ambiente *conda* para programação do veículo autônomo. Quaisquer dúvidas, fiquem a vontade para entrar em [contato](/AVL/pt/contato/).

***
# 1. Windows

Baixe os arquivos dos *releases* compactados, e coloque-os em um diretório onde deseja rodar a aplicação:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/releases.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/releases.png" alt="releases" title="releases" />
</a>

Extraia os arquivos: 

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/zip.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/zip.png" alt="zip" title="zip" />
</a>

Entre na pasta \AVL\Unreal Environments\SimpleMaze\ e clique duas vezes no arquivo *run.bat*. Ele rodará um ambiente desenvolvido na Unreal Engine em baixa resolução:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/run_bat.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/run_bat.png" alt="run_bat" title="run_bat" />
</a>

Copie o arquivo *settings.json* da pasta \AVL\json\ e substitua na pasta C:\Users\\$Nome do Usuário$\Documents\AirSim\

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/json.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/json.png" alt="json" title="json" />
</a>  

## 1.1. Configurando o Ambiente do Conda

A configuração do ambiente serve especificamente para utilizar as mesmas versões de pacotes tanto do conda quanto do python. Isso garantirá que execute exatamente as mesmas versões que nós em sua máquina. Para isso, pode ser utilizado dois métodos para essa configuração, o pelo Anaconda Navigator na Seção 1.1.1, e pelo próprio prompt de comando do Windows na Seção 1.1.2. A instalação por um dos métodos já é suficiente, então, escolha com sabedoria. :) 

É importante ressaltar que o Anaconda deve estar atualizado para sua última versão!

### 1.1.1. Anaconda Navigator

Após instalar o Anaconda, abra o Anaconda Navigator e clique em *Environments*:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav1.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav1.png" alt="conda_nav1" title="conda_nav1" />
</a>  

Na aba *Environments*, clique em *import*:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav2.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav2.png" alt="conda_nav2" title="conda_nav2" />
</a> 

Clique no ícone da pasta e localize o arquivo avl.yml, ele se encontra no diretório /AVL/. Em seguida clique em *import*:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav3.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav3.png" alt="conda_nav3" title="conda_nav3" />
</a> 

O processo demora alguns minutos, então aproveite para tomar o seu chá/café preferido.

Após terminado, clique na aba *Home* do Anaconda Navigator e confira se o **ambiente selecionado é o AVL**. Com isso, podemos executar o Spyder:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav4.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav4.png" alt="conda_nav4" title="conda_nav4" />
</a> 

Com o Spyder rodando, clique na pasta para importar os arquivos:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav5.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav5.png" alt="conda_nav5" title="conda_nav5" />
</a> 

Importe os arquivos *Tournament.py* e *TeamsMethods.py* da pasta *files* e *Run.py* do diretório principal:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav6.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav6.png" alt="conda_nav6" title="conda_nav6" />
</a> 

Com isso, seu PC pode começar a executar o simulador. Siga para a página [Guia Inicial](/AVL/pt/primeiros-passos/guia/) para configurar rodar os exemplos e programar seu próprio carro! 


### 1.1.2. Prompt de Comando

Para utilizar o Prompt de Comando é necessário primeiro alterar as variáveis de ambiente do sistema, para rodar o comandos do conda. Digite na guia do Windows: "Variáveis de Ambiente" e clique na primeira opção que aparecer:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_1.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_1.png" alt="cmd_1" title="cmd_1" />
</a> 

Na aba Avançado, clique em Variáveis de Ambiente:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_2.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_2.png" alt="cmd_2" title="cmd_2" />
</a> 

Ache na guia Variáveis de Sistema a Variável PATH e clique duas vezes:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_3.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_3.png" alt="cmd_3" title="cmd_3" />
</a> 

Em uma linha vazia, clique duas vezes e adicione os seguintes caminhos:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_4.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_4.png" alt="cmd_4" title="cmd_4" />
</a> 

Clique em OK, em todas as telas abertas. Agora é possível inicializar o conda através do Prompt de Comando.

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_5.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_5.png" alt="cmd_5" title="cmd_5" />
</a> 

Copie o caminho do diretório da pasta AVL:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_6.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_6.png" alt="cmd_6" title="cmd_6" />
</a> 

Digite no cmd o Comando cd e cole o caminho copiado apertando o botão direito do *mouse* e aperte Enter:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_7.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_7.png" alt="cmd_7" title="cmd_7" />
</a> 

Copie o seguinte código para o Prompt e aperte Enter: 
```
conda env create -f avl.yml
```
<a href="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_8.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/cmd_8.png" alt="cmd_8" title="cmd_8" />
</a> 

O processo demora alguns minutos, então aproveite para tomar o seu chá/café preferido.

Digite o seguinte código no Prompt:

```
conda activate avl
spyder
```

Com isso, executaremos o Spyder. Com o Spyder rodando, clique na pasta para importar os arquivos:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav5.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav5.png" alt="conda_nav5" title="conda_nav5" />
</a> 

Importe os arquivos *Tournament.py* e *TeamsMethods.py* da pasta *files* e *Run.py* do diretório principal:

<a href="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav6.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/installation/conda_nav6.png" alt="conda_nav6" title="conda_nav6" />
</a> 

Com isso, seu PC pode começar a executar o simulador. Siga para a página [Guia Inicial](/AVL/pt/primeiros-passos/guia/) para configurar rodar os exemplos e programar seu próprio carro! 

***
# 2. Linux

A configuração para o ambiente Linux está sendo desenvolvida, acompanhe atualizações na guia de [Notícias](/AVL/pages/news/).

***

# 3. MacOS

A configuração para o ambiente MacOS está sendo desenvolvida, acompanhe atualizações na guia de [Notícias](/AVL/pages/news/).

***

# 4. Observações

## 4.1. Clonando o Repositório

É possível clonar o repositório, mas devido aos limites de transferência do *GitHub* o repositório não apresenta os ambientes de simulação, <span style="color:red">sendo de responsabilidade do usuário</span> baixar os ambientes configurados com o AirSim. Os mesmos podem ser encontrados [aqui](https://github.com/microsoft/AirSim/releases). Para clonar o repositório, execute o **Git-Bash** e direcione o ambiente para o diretório desejado de sua máquina utilizando o comando *cd* e *ls*. Após digite o seguinte código no terminal:

```
git clone https://github.com/SIR-research/AVL.git
```

As versões de arquivos que se encontram no repositório (*branch master*) da competição serão utilizados para atualização interna e testes de novos comandos do simulador, assim novamente, recomendamos que utilizem os *releases*.
