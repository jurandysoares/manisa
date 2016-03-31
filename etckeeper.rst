Guardião do diretório /etc
============================

O primeiro passo é a instalação do pacote *etckeeper*, que gerenciará todas as alterações feitas no diretório de configurações globais do Linux, isto é, o diretório `/etc`. Para tanto, execute::

    sudo apt install etckeeper

Por trás, o *etckeeper* utiliza o sistema distribuído de controle de versão `Git <https://git-scm.com/>`_. Para deixar registrado quem você é, é fortemente recomendado que você configure informações sobre seu usuário. Faça isto digitando os comandos abaixo::

    git config --global user.name "Nome Sobrenome"
    git config --global user.email "nome.sobrenome@escolar.ifrn.edu.br"

Depois de configurado seu usuário, você poderá registrar qualquer configuração nova feita no sistema por meio do comando::

    sudo etckeeper commmit "Mensagem de consolidação"


