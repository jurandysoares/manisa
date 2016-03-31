Alteração do menu de carregamento dos sistemas operacionais
=============================================================

Após instalado e configurado o etckeeper, recomendo fortemente: (1) a alteração da ordem de início dos sistemas operacionais, dando preferência ao Windows (Sim, somos cavalheiros!); (2) a remoção do modo de recuperação do Ubuntu; e (3) a desabilitação do teste de memória.

#. Troca da ordem de opções de sistemas operacionais que podem ser carregados::

    sudo mv /etc/grub.d/{30,07}_os-prober

#. Remoção do modo de recuperação do Ubuntu::

    sudo sed -i 's/^#\(GRUB_DISABLE_RECOVERY="true"\)/\1/g' /etc/default/grub

Para compreender melhor o funcionamento do comando `sed`, recomendo a leitura de `Unix Sed Tutorial: Advanced Sed Substitution Examples <www.thegeekstuff.com/2009/10/unix-sed-tutorial-advanced-sed-substitution-examples/>`_.

#. Desabilitação do teste de memória::

    sudo chmod -x /etc/grub.d/20_memtest86+

Feito os três passos acima, podemos então atualizar a lista de opções do menu do Grub::

    sudo update-grub

O comando acima deve gerar uma saída parecida com o texto abaixo::

    Generating grub configuration file ...
    Found Windows 7 (loader) em /dev/sda1
    Encontrado imagem linux: /boot/vmlinuz-4.4.0-16-generic
    Encontrado imagem initrd: /boot/initrd.img-4.4.0-16-generic
    Encontrado imagem linux: /boot/vmlinuz-4.4.0-10-generic
    Encontrado imagem initrd: /boot/initrd.img-4.4.0-10-generic
    concluído

Da próxima vez que você reiniciar a máquina você verá a diferença. O Windows serão o sistema operacional padrão para carregar. Antes de reiniciar a máquina, vamos registrar as alterações feitas utilizando o :doc:`etckeeper <etckeeper>`::

    sudo etckeeper commit "Grub: alteração da lista de opções de sistemas operacionais"

Quer ver como ficou? Então execute::

    sudo shutdown -r now

Ou simplesmente::

    sudo reboot


