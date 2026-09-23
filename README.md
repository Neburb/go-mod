# Go World — public releases

Este repositorio distribuye las versiones instalables de Go World. El código fuente y las pruebas viven en el repositorio privado `Neburb/gen1recomp-go`; aquí se publican únicamente el ZIP del mod y su suma SHA-256.

## Instalar

Descarga `go_world-VERSION.zip` de [Releases](https://github.com/Neburb/go-mod/releases). Cierra Gen1Recomp y sustituye el ZIP anterior completo. No mantengas dos versiones activas. En Android, el flujo `GO-GPS-automate.flo` se incluye en el ZIP; consulta el `README.md` incluido para requisitos y límites.

## Publicación

Cuando la CI del repositorio privado termina correctamente en `main`, envía el SHA exacto a este repositorio. La acción de publicación obtiene ese commit privado, crea un ZIP con `manifest.json` apuntando a `Neburb/go-mod`, comprueba el contenido y publica una release `vVERSION` con `go_world-VERSION.zip` y `sha256sums.txt`. Una versión ya publicada no se sustituye: aumenta `manifest.json` antes de la siguiente publicación.

Para configurar la automatización, guarda el mismo token de GitHub de grano fino en los secretos de Actions de ambos repositorios. Debe tener **Contents: read** sobre `Neburb/gen1recomp-go` y **Contents: read and write** sobre `Neburb/go-mod`. Llámalo `SOURCE_REPO_TOKEN` aquí y `RELEASE_REPO_TOKEN` en el privado. El token se usa solo en las acciones y no entra en el ZIP.
