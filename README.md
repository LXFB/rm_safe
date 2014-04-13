RM safe
=======

Es una modificaciòn que realicè sobre el comando rm.
Evita eliminar directorios de la raiz del sistema por error.
Puede deshabilitarse temporalmente pasandole el argumento --s.

La forma mas ràpida de crear el binario y evitar problemas de librerias etc
es construirlo desde coreutils.

### CONSTRUCCION
 
    cd /tmp
    git clone github.com/LXFB/rm_safe.git
    git clone git://git.sv.gnu.org/coreutils
    cd coreutils
    ./bootstrap
    ./configure
    cp ../rm_safe/src/* src/
    make

### PRUEBA

    cd src
    ./rm -R /tmp
      rm: cannot remove '/tmp': Operaciòn cancelada
      System directory. Use '--s'

### INSTALACION

    mv /usr/bin/rm /usr/bin/rm.bk
    mv rm /usr/bin/
