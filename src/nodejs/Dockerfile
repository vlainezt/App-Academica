FROM node

# Información de Metadata
LABEL "sv.tc-ugb.appNode"="Team Cilantro SV - UGB"
LABEL maintainer="Team Cilantro"
LABEL version="1.0"


# Crear directorio de trabajo
RUN mkdir -p /opt/app

# Se estable el directorio de trabajo
WORKDIR /opt/app

# Instala los paquetes existentes en el package.json
COPY /server/package.json .
RUN npm install --quiet

# Instalación de Nodemon en forma Global
# Al realizarse cambios reiniciar el servidor
RUN npm install nodemon -g --quiet

# Copia la Aplicación
COPY /server/. .

# Expone la aplicación en el puerto 3001
EXPOSE 3001

# Inicia la aplicación al iniciar al contenedor
CMD nodemon -L --watch . chatServer.js
