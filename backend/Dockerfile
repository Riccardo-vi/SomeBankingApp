# Immagine di base Python leggera 

FROM python:3.10-slim 
# Directory di lavoro nel container 
WORKDIR /app 


# Copia di tutto il codice sorgente del backend 
RUN apt-get update && apt-get install -y git
RUN git clone https://github.com/Riccardo-vi/SomeBankingApp.git .

WORKDIR /app/backend

RUN pip install -r requirements.txt

# Esposizione della porta 8000 (porta di default per FastAPI) 
EXPOSE 8000 

# Comando di avvio a runtime con Uvicorn 
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
