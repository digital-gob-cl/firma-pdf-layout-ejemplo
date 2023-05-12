# firma-pdf-layout-ejemplo
Ejemplo para la integración con API firmaGob que permite firmar archivo en formato PDF agregando además un componente visible en el documento 

En el ejemplo se muestra como generar el base 64 del archivo PDF y el xml para el layout, realizar la petición a la API creando la estructura requerida para el body, además un ejemplo para generar JWT y como procesar la respuesta de la API.

## Variables de ambiente necesarias

- ENTITY: Código asociado a la institución a la cual pertenece el titular (string), para ambiente de test usamos "Subsecretaría General de la Presidencia"
- API_TOKEN_KEY: Campo no encriptado de tipo string que contiene el código único generado a partir del registro de la aplicación, para ambiente de test usamos "sandbox"
- RUN: Run identificador del titular de fima, no debe contener puntos, guión ni tampoco el dígito verificador (string). Para ambiente de test usamos "22222222"
- PURPOSE: Código asociado al tipo de certificado a utilizar (string) para ambiente de test usamos "Desatendido"
- SECRET_KEY: Secreto para jwtToken, para ambiente de test usamos "27a216342c744f89b7b82fa290519ba0"
- ENDPOINT_API: URL de la api, para ambiente de test usamos https://api.firma.cert.digital.gob.cl/firma/v2/files/tickets

## Consideraciones
- La imagen contenida en el archivo [firma1.png] es una muestra que se incrusta en el PDF firmado
- El formato del layout se encuentra el archivo [layout.xml]

### Variables layout
- llx: Coordenada x de la esquina inferior izquierda de la imagen. Número entero
- lly: Coordenada y de la esquina inferior izquierda de la imagen. Número entero
- urx: Coordenada x de la esquina superior derecha de la imagen. Número entero
- ury: Coordenada y de la esquina superior derecha de la imagen. Número entero
- page: Número de página donde se incluirá Número entero. También es posible usar la palabra LAST para hacer referencia a la última hoja del documento.
- image: Tipo de encoding utilizado para embeber la imagen Texto. Valor constante a utilizar BASE64
- base64value: Contenido del archivo en base64