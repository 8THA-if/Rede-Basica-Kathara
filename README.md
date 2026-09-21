# Rede-Básica-Kathará

* ### Necessário para rodar:
    - [WSL Latest](https://github.com/microsoft/WSL/releases "Releases do WSL") instalado
    - [Kathara](https://www.kathara.org/download.html "Página de download") instalado
    - [Docker desktop](https://docs.docker.com/desktop/ "Downloads no final da página") aberto
    - Abra a pasta clonada no cmd e digite o seguinte comando:
          "``` mkdir r0, r1, pc0, pc1, pc2, pc3 ```"
      > Isso ira criar as pastas necessárias para que a emulação funcione

* ### Inicialização:
    - Ainda no cmd da pasta clonada, utilize "```kathara lstart```" para iniciar a emulação
      > Após iniciá-la, use "```kathara list```" caso queira mais detalhes sobre a emulação

* ### Testes:
    - Todas os computadores e roteadores estão conectados entre si:
        - Utilize ```ping [ip da máquina]``` para testar essas conexões
          > O roteador ```r1``` tem uma "ponte" para se conectar com a internet real, você pode pingar ips reais utilizando qualquer uma das máquinas presentes na emulação
        - Utilize ```traceroute [ip da máquina]``` para ver o caminho que o pacote precisa tomar para que chegue em outra máquina

### Topologia:

<img width="737" height="581" alt="LabTopologia" src="./assets/LabTopologia.jpg" />

[Topologia no Draw.io](https://drive.google.com/file/d/1WPr9Ei1yLDAToAIUH0xiuMwlwGKGnEY1/view?usp=sharing)

### Tabela de Rede:
| Rede | Prefixo | Dispositivo | Interface | Endereço IP | Função |
| :---: | --- | :---: | :---: | --- | --- |
| A | 192.168.1.0/24 | pc0 | eth0 | 192.168.1.2 | Host |
| A | 192.168.1.0/24 | pc1 | eth0 | 192.168.1.3 | Host |
| A | 192.168.1.0/24 | r0 | eth0 | 192.168.1.1 | Gateway |
| B | 192.168.2.0/30 | r0 | eth1 | 192.168.2.1 | Roteador |
| B | 192.168.2.0/30 | r1 | eth1 | 192.168.2.2 | Roteador |
| C | 192.168.3.0/24 | r1 | eth0 | 192.168.3.1 | Gateway |
| C | 192.168.3.0/24 | pc2 | eth0 | 192.168.3.2 | Host |
| C | 192.168.3.0/24 | pc3 | eth0 | 192.168.3.3 | Host |

### To do:
* #### ~~Reorganizar topologia de rede~~
