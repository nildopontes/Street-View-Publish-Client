# pano-api
Um cliente web simplificado para enviar e gerenciar fotos panorâmicas 360 para o Street View utilizando a Street View Publish API.

Acesse este guia do Google para criar e configurar a autenticação <https://developers.google.com/streetview/publish/first-app?hl=pt-br>.

## Alguns exemplos de uso:

### Enviar uma foto
```javascript
newToken().then(t => {
   getUploadURL(t).then(uploadUrl => {
      sendImageData(t, 'file', uploadUrl).then(() => {
         sendMetadata(t, uploadUrl, '-9.313995', '-35.940649');
      });
   });
});
```
### Apagar uma foto
```javascript
newToken().then(t => {
   deletePhoto(t, 'CAoSLEFGMVFpcE1qOEFKUG43UXpPbXV1R3VLSFRWVnpTdjdSUFhVWEstUWpCR3c1');
});
```
### Criar uma conexão recíproca entre 2 imagens
```javascript
newToken().then(t => {
   updateConnections(t, 'CAoSLEFGMVFpcE1qOEFKUG43UXpPbXV1R3VLSFRWVnpTdjdSUFhVWEstUWpCR3c1', 'CAoSLEFGMVFpcFBSQm40ZjJTckl3cVVoQUVhdHFfV181SXgxZnAyMm00aEltdnp1');
});
```
