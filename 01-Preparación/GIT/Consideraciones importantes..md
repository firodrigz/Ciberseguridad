ESTADO:
git status --> estado del commit.

ÁREA DE PREPARACIÓN:
git add <file> <file> --> agrego archivo proximo a comitear.

git rm --cached <file>  --> saco archivo de área de preparación.

COMMIT:
git commit -m "commit" --> del área de preparación se suben.

REDUCIR MUESTRA EN LOG:
git config --global core.abbrev 6

---

TIPS:

COMMIT EVITANDO GIT ADD:
git commit -m "commit" -a -> -a para subir todos los archivos, no hace falta hacer un git add.

PONER DESCRIPCIÖN COMMIT EN VISUAL:
git commit


REGRESAR VERSIÓN COMMIT ATRÁS:
git checkout archivo.txt --> vuelvo a la versión anterior commiteada. IMPORTANTE NO SUBIR AL ÁREA DE PREPARACIÓN.

git reset --hard --> fuerza a volver al último commit SIN IMPORTAR que existan CAMBIOS en el ÁREA DE PREPARACIÓN.

RENOMBRAR FICHERO:
git mv <file> <nuevonombre>

VER/COMPARAR CUALES SON LOS CAMBIOS ENTRE COMMIT Y NO COMMITEADO:
git log --oneline --> sacar el hash
git diff --word-diff <hash+viejo> <hash>

MODIFICAR Y DESHACER COMMITS:

ÚLTIMO COMMIT:
git commit --amend

DESHACER COMMITS:
git reset --soft <hashcommitanterior>
git reset --soft head~1






