# Resumo do projeto

Criação de uma VM Ubuntu:21:04 LTS utilizando Vagrant e utilizando o Ansible para instalar o Docker com alguns pacotes, e executar um container do nginx expondo para a porta 8080, com uma página web.

# Pacotes instalados

- ``vim``
- ``curl``
- ``htop``
- ``nmap``
- ``telnet``
- ``net-tools``
- ``wget``
- ``unzip``
- ``ca-certificates``
- ``gnupg-agent``
- ``lsb-release``
- ``python3-pip``
- ``python3-setuptools``
- ``docker-ce``
- ``docker-ce-cli``
- ``containerd.io``
- ``docker-compose-plugin``

# Tecnologias utilizadas

- ``Vagrant``
- ``VirtualBox``
- ``Ansible``
- ``Docker``

# Como testar a máquina

- ``Fazer a instalação do virtualbox``
```
sudo apt-get install virtualbox
```
- ``Fazer a instalação do Vagrant``
```
$ wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
$ echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | $ sudo tee /etc/apt/sources.list.d/hashicorp.list
$ sudo apt update && sudo apt install vagrant
```
- ``Fazer a instalação do Ansible``
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```
- ``Utilizar o comando no terminal para iniciar a máquina``
```
vagrant up
```
- ``Editar o arquivo "server" inserindo o ip da sua máquina virtual``
- ``Configurar o SSH da sua máquina para comunicar com a máquina virtual``
```
ssh-copy-id -i ~/.ssh/id_rsa vagrant@ip-da-sua-máquina-virtual
```
- ``Utilizar o comando no terminal para executar o ansible``
```
ansible-playbook -i server main.yml
```
