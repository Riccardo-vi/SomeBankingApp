# Immagine di base Python leggera 

FROM python:3.10-slim 
# Directory di lavoro nel container 
WORKDIR /app 

# Copia e installazione delle dipendenze 
COPY requirements.txt . 
RUN pip install -r requirements.txt 

# Copia di tutto il codice sorgente del backend 
COPY . . 

# Esposizione della porta 8000 (porta di default per FastAPI) 
EXPOSE 8000 

# Comando di avvio a runtime con Uvicorn 
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]