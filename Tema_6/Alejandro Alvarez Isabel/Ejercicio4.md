# Ejercicio 4: Gestión de eventos

| Método HTTP | URI                 | Query Params  | Cuerpo de la Petición                                           | Cuerpo de la Respuesta                                                  | Códigos de Respuesta                  |
|-------------|---------------------|---------------|-----------------------------------------------------------------|-------------------------------------------------------------------------|---------------------------------------|
| GET | /events | city, date, type | N/A                                                             | { "events": [{ "id": 1, "name": "Sala Cocó", "type": "meeting_room" }] } | 200 OK                                |
| POST | /events | N/A | { "name": "Auditorio", "type": "auditorium", "city": "Madrid" } | { "eventId": 101, "name": "Auditorio" }                            | 201 Created                           |
| PATCH | /events/{id} | N/A | { "name": "Sala Apollo" }                                       | { "eventId": 1, "name": "Sala Apollo" }                                 | 200 OK <br> 404 Not Found             |
| DELETE | /events/{id} | N/A | N/A                                                             | { "message": "event removed" }                                          | 200 OK                                |
| POST | /bookings | N/A | { "eventId": 1, "userId": 50, "date": "2024-06-10" }            | { "bookingId": 500, "status": "confirmed" }                             | 201 Created<br> 409 Conflict          |
| PUT | /bookings/{id} | N/A | { "eventId": 1, "date": "2024-06-11" }                          | { "bookingId": 500, "date": "2024-06-11" }                              | 200 OK<br> 400 Bad Request            |
| DELETE | /bookings/{id} | N/A | N/A                                                             | { "message": "Booking cancelled" }                                      | 200 OK                                |
| POST | /events | N/A | { "title": "Tech Talk", "eventId": 101, "date": "2024-07-01" }  | { "eventId": 20, "title": "Tech Talk" }                                 | 201 Created <br> 422 Unprocessable Entity |