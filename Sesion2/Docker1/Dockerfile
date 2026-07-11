#Definir la imagen base
FROM python:3.9-slim

#Instalaciones de sistyemas y actualizaciones 
RUN pi3 install --upgrade pip &&
    pip3 install notebook==6.5.6

#se define el directorio
WORKDIR /workspace

#Donde almacemar los archivos de configuracion
RUN mkdir -p /root/.jupyter

#ingresar las variables
RUN echo "c.NotebookApp.token =''" >> /root/.jupyter/jupyter_motebook_config.py && \
    echo "c.NotebookApp.password =''" >> /root/.jupyter/jupyter_motebook_config.py && \
    echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_motebook_config.py && \
    echo "c.NotebookApp.open_browser = False" >> /root/.jupyter/jupyter_motebook_config.py

#Puerto de exposicion
EXPOSE 8888

#EJECUCION DE LA APLICACION
CMD ["jupyter","notebook","--ip=0.0.0.0","--port=888","--no-browser","--allow-root"]
    
