Usuário
========

Para criação de um novo usuário para você, utilize o seguinte comando::

  sudo useradd \
  > --base-dir /home \
  > --comment "Nome Sobrenome,matricula,dd/mm/aaaa,sexo" \
  > --create-home \
  > --shell /bin/bash \
  > --password $(openssl passwd -1 -salt xyz sua_senha) \
  > nome

Exemplo::

  sudo useradd \
  > --base-dir /home \
  > --comment "Junior Silva,20164345345345,12/07/1983,M" \
  > --create-home \
  > --shell /bin/bash \
  > --password $(openssl passwd -1 -salt xyz 123456) \
  > junior


Referências
============

* `Manually generate password for /etc/shadow <http://unix.stackexchange.com/questions/81240/manually-generate-password-for-etc-shadow>`_
* `Linux Shadow Password HOWTO: Why shadow your passwd file? <http://www.tldp.org/HOWTO/Shadow-Password-HOWTO-2.html>`_
* `useradd(8) - Linux man page <http://linux.die.net/man/8/useradd>`_
