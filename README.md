rm safe
=======

Es una modificación que realicé sobre el comando rm.
Evita eliminar directorios de la raiz del sistema por error.
Puede deshabilitarse temporalmente pasandole el flag --s.

La forma mas rápida de crear el binario y evitar posibles problemas, 
es construirlo desde coreutils.

### CONSTRUCCION
 
    cd /tmp
    git clone https://github.com/LXFB/rm_safe.git
    git clone git://git.sv.gnu.org/coreutils
    cd coreutils
    ./bootstrap
    ./configure
    cp ../rm_safe/src/* src/
    make

### PRUEBA

    cd src
    sudo chmod +x rm
    sudo ./rm -rf /*
      rm: cannot remove '/': Operaciòn cancelada
      System directory. Use '--s'

### INSTALACION

    sudo mv /usr/bin/rm /usr/bin/rm.bk
    sudo mv rm /usr/bin/
