---
layout: single
title: "Guia Inicial"

permalink: /pt/primeiros-passos/guia/

sidebar:
    nav: "primeiros-passos"
    
toc: true
toc_label: "Conteúdo"
toc_icon: "cog"
---

Após realizado as configurações necessárias para inicializar o simulador, será possível programar o seu próprio carro autônomo. Abra a pasta descompactada da AVL:

<a href="{{ site.baseurl }}/assets/images/getting-started/quick/cmd1.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/quick/cmd1.png" alt="cmd1" title="cmd1" />
</a>

Clique duas vezes no caminho da pasta, apague as informações, digite cmd e aperte enter. Isso abrirá um prompt de comando na pasta AVL:

<a href="{{ site.baseurl }}/assets/images/getting-started/quick/cmd2.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/quick/cmd2.png" alt="cmd2" title="cmd2" />
</a>

Copie o seguinte código para o Prompt e aperte Enter: 
```
conda activate avl
```

<a href="{{ site.baseurl }}/assets/images/getting-started/quick/cmd3.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/quick/cmd3.png" alt="cmd3" title="cmd3" />
</a>

Agora, copie e cole o seguinte código para executar o AVSim
```
python AVSim.py
```

<a href="{{ site.baseurl }}/assets/images/getting-started/quick/cmd4.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/quick/cmd4.png" alt="cmd4" title="cmd4" />
</a>

Com isso, o AVSim estará ativado. Toda vez que for rodar o simulador, lembre-se de executar esses passos anteriores.

<a href="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_1.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_1.png" alt="AVSim_1" title="AVSim_1" />
</a>

# 1. AVSim

O AVSim é um simulador para veículos autônomos, sendo possível escolher tanto o ambiente de simulação desejado quanto o algoritmo a ser executado. Ainda em fase de desenvolvimento, o AVSim permitirá controle de variáveis climáticas e observação de parâmetros de interesse como posição do veículo no mapa e perfis de velocidade e direção do volante. Alguns códigos de exemplos encontram-se na pasta /AVL/Teams/, como o Team1.py e o Team2.py. Para testá-los, selecione o mapa **City** e clique em *LAUNCH*.

<a href="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_2.png">
	<img src="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_2.png" alt="AVSim_2" title="AVSim_2" />
</a>

Com o ambiente de simulação aberto, selecione o código *Team1.py*, ou *Team2.py*. As explicações e detalhes dos códigos se encontram na Seção ?.?.?. **LEIA A SEÇÃO INDICADA PARA COMPREENDER A EXECUÇÃO DO CÓDIGO**

## 1.1 Estrutura de Arquivos

O AVSim é dividido em diversos arquivos que realizam a comunicação com o simulador e executam o controle do carro. O arquivo que gerencia esse controle é o *Tournament.py*, localizado na pasta /AVL/files/.

### 1.1.1 Tournament.py

*Tournament.py* possui todas as variáveis para permitir a comunicação da Unreal com o python, através do <a href="https://microsoft.github.io/AirSim/" target = "_blank" title = "AirSim">AirSim</a> da Microsoft. Ele possui duas classes principais, a *Tournament* e a *CarMethods*.

#### 1.1.1.1 Classe Tournament

A classe *Tournament* controla os parâmetros para lançar o ambiente de simulação, como por exemplo:

- **Modo de Controle:** Manual ou Automático;

	No início de todo o código, o programa pergunta qual modo de controle deve ser executado, esperando do usuário uma resposta.

	<a href="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_3.png">
		<img src="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_3.png" alt="AVSim_3" title="AVSim_3" />
	</a>
- Configurações de Clima e Tempo;

	Descomente o código e faça a alteração do dia (AAAA-MM-DD) e horário (HH:MM:SS):

	```python
	## Setting Day and Hour of the Environment
    self.getClient().simSetTimeOfDay(True,'2020-07-10 14:00:00')
	```
- Posição Inicial de Objetos ou Veículos;

	A posição inicial de veículos é controlada pela *Pose* do objeto, sendo necessário passar um array de Posição (x,y,z) e um array de Orientação (*row*, *pitch*, *yaw*) em radianos.

	```python
	position = airsim.Vector3r(-214.6370086669922,207.1434326171875,-0.440409541130066)
    orientation = airsim.utils.to_quaternion(0,0,(90*3.1415)/180)
    initialPose = airsim.Pose(position,orientation)
    self.__setVehiclePose(initialPose)
    ```
- Controle de Colisão com Objetos do Cenário;
	
	Toda vez que o veículo colide com algum objeto em cena, o programa executado para de rodar, finalizando todos os processos. Além disso, mostra as propriedades do objeto colidido:

	<a href="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_4.png">
		<img src="{{ site.baseurl }}/assets/images/getting-started/quick/AVSim_4.png" alt="AVSim_4" title="AVSim_4" />
	</a>
- Controle de *Threads*;
- Atualização e Armazenamento de Parâmetros de Interesse:
	- Mapa de Posição;
	- Perfil de Velocidade do Veículo;
	- Perfil do Acelerador do Veículo;
	- Perfil de Direção do Volante;
	- Perfil do Freio do Veículo.


#### 1.1.1.2 Classe CarMethods

### 1.1.2 TeamsMethods.py



### 1.1.3 Pasta Teams 

#### 1.1.3.1 Team1.py

Team1.py é um código que executa três processos em paralelo para o controle do carro. Esses processos são dividos em Controle Lateral

#### 1.1.3.2 Team2.py

#### 1.1.3.3 TeamDefault.py

#### 1.1.3.4 Crie Seu Próprio Time

Para criar e executar seu código personalizado, faça uma cópia do arquivo *TeamDefault.py* na pasta /AVL/Teams/. Coloque o nome do seu Time no nome do arquivo, substituindo *TeamDefault.py* por *SeuNome.py*

Abra o arquivo *SeuNome.py* e *__init__.py* com qualquer editor de texto. Recomendamos que utilize o Spyder, já instalado no ambiente AVL do conda. Altere o seguinte código, substituindo *TeamDefault* por *SeuNome*

```python
class SeuNome(TeamsMethods,object):
```

Acrescente *SeuNome* no arquivo *__init__.py*:

```python
__all__ = ['Team1','Team2', 'TeamDefault', 'SeuNome']
```

Execute o AVSim novamente. Realizando os passos iniciais.
--- 

# 1. OUTPUT CONTROLS

## GAS

## BRAKE

## STEERING

--- 

# 2. INPUT DATA ACESS

## CAMERA

## LIDAR

## SONAR

## RADAR
