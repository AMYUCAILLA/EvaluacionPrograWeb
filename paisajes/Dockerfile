# Usar una imagen base de Node
FROM node:14-alpine

# Establecer el directorio de trabajo en /app
WORKDIR /app

# Copiar package.json y package-lock.json al directorio de trabajo
COPY package*.json ./

# Instalar las dependencias del proyecto
RUN npm install

# Copiar el resto de los archivos del proyecto al directorio de trabajo
COPY . .

# Construir el proyecto de React
RUN npm run build

# Instalar un servidor HTTP para servir el contenido de la aplicación y exponer el puerto 80
RUN npm install -g serve
CMD ["serve", "-s", "build"]

# Exponer el puerto en el que se ejecutará la aplicación
EXPOSE 80
