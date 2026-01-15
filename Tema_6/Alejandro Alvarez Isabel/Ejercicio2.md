| Método HTTP | URI                 | Query Params  | Cuerpo de la Petición                              | Cuerpo de la Respuesta                    | Códigos de Respuesta                                    |
|-------------|---------------------|---------------|----------------------------------------------------|-------------------------------------------|---------------------------------------------------------|
| POST | /movies | N/A | {"title": "Inception", "duration": 148}            | {"movieId": 1, "title": "Inception"}      | 201 Created <br> 400 Bad Request   |
| PUT | /movies/{id} | N/A | {"title": "Inception", "duration": 150}            | {"movieId": 1, "title": "Inception"}      | 200 OK <br> 404 Not Found          |
| DELETE | /movies/{id} | N/A | N/A                                                | {"message": "Movie deleted"}              | 200 OK <br> 404 Not Found             |
| POST | /rooms | N/A | {"name": "Sala 1", "capacity": 50}                 | {"roomId": 10, "name": "Sala 1"}          | 201 Created                        |
| PATCH | /rooms/{id} | N/A | {"capacity": 60}                                   | {"roomId": 10, "capacity": 60}            | 200 OK <br> 404 Not Found             |
| POST | /users | N/A | {"name": "Alejandro", "email": "aai@mail.com"}     | {"userId": 5, "name": "Alejandro"}        | 201 Created                        |
| PATCH | /users/{id} | N/A | {"email": "aai@mail.com"}                          | {"userId": 5, "email": "aai@mail.com"}    | 200 OK                             |
| POST | /bookings | N/A | {"userId": 5, "roomId": 10, "seats": ["A1", "A2"]} | {"bookingId": 100, "status": "pending"}   | 201 Created <br> 409 Conflict         |
| PUT | /bookings/{id} | N/A | {"seats": ["B1", "B2"]}                            | {"bookingId": 100, "seats": ["B1", "B2"]} | 200 OK <br> 400 Bad Request           |
| DELETE | /bookings/{id} | N/A | N/A                                                | {"message": "Booking cancelled"}          | 200 OK <br> 404 Not Found             |
| POST | /bookings/{id}/payments | N/A | {"method": "credit_card", "amount": 15.50}         | {"paymentId": 99, "status": "confirmed"}  | 201 Created <br> 402 Payment Required |
