# fastapi_conexion

Cada vez que mi celular recibe la notificación Yape, la aplicación va a detectar el depósito, extrae los datos y va a enviar una petición HTTP con el método POST a mi FASTAPI.

## El formato JSON que envia la app

```json
{
  "sender": "JUAN PEREZ",
  "amount": 25.50,
  "currency": "S/",
  "timestamp": 1729352400000,
  "date_formatted": "19/10/2026 10:20:00",
  "type": "YAPE",
  "status": "APPROVED",
  "message": "¡Yapeaste! JUAN PEREZ te envió S/ 25.50"
}

```

- Averiguar la IP con ipconfig
- Configurar la URL `http://192.168.1.35:8000/webhook/yape`


## Código en FastAPI

```python
from fastapi import FastAPI, Header, HTTPException, status
from pydantic import BaseModel
from typing import Optional
import uvicorn

app = FastAPI(title="Yape Webhook Listener")

# Token de seguridad opcional (si lo configuraste en la app)
SECRET_API_KEY = "mi_clave_secreta_123"

# Modelo que coincide con los datos que manda la app
class YapeNotification(BaseModel):
    sender: str
    amount: float
    currency: str = "S/"
    timestamp: int
    date_formatted: str
    type: str = "YAPE"
    status: str = "APPROVED"
    message: str

@app.post("/webhook/yape", status_code=status.HTTP_200_OK)
async def receive_yape_payment(
    payment: YapeNotification,
    authorization: Optional[str] = Header(None)
):
    # Validación opcional de Token de seguridad
    # if authorization != f"Bearer {SECRET_API_KEY}":
    #     raise HTTPException(status_code=401, detail="Token no autorizado")

    print("=" * 40)
    print("🔔 ¡NUEVO PAGO DE YAPE RECIBIDO!")
    print(f"👤 De: {payment.sender}")
    print(f"💰 Monto: {payment.currency} {payment.amount:.2f}")
    print(f"🕒 Fecha: {payment.date_formatted}")
    print(f"📱 Mensaje original: {payment.message}")
    print("=" * 40)

    # AQUÍ HACES LO QUE NECESITES CON EL PAGO:
    # - Guardarlo en tu base de datos (PostgreSQL, MySQL, SQLite, MongoDB)
    # - Activar un pedido en tu tienda web
    # - Imprimir un ticket o comanda
    # - Mandar mensaje a Telegram / WhatsApp

    return {
        "status": "success",
        "message": "Pago recibido correctamente",
        "received_amount": payment.amount,
        "sender": payment.sender
    }

if __name__ == "__main__":
    # 0.0.0.0 permite que otros dispositivos (como tu celular) se conecten
    uvicorn.run("main:app", host="0.0.0.0", port=8000, reload=True)
```

