# Ejercicio 3: Restaurante

| Método HTTP | URI                 | Query Params  | Cuerpo de la Petición                              | Cuerpo de la Respuesta                                     | Códigos de Respuesta                                    |
|-------------|---------------------|---------------|----------------------------------------------------|------------------------------------------------------------|---------------------------------------------------------|
| GET         | /restaurants | location, cuisine | N/A | {"restaurants": [{"id": 1, "name": "Pizzeria"}]}           | 200 OK | 
| GET         | /restaurants/{id}/dishes | N/A | N/A | {"menu": [{"dishId": 10, "name": "Pizza", "price": 12.0}]} | 200 OK<br> 404 Not Found| 
|  POST        | /restaurants/{id}/dishes | N/A | {"name": "Sushi Roll", "price": 15.0} | {"dishId": 11, "status": "available"}                      | 201 Created| 
|  PATCH       | /restaurants/{id}/dishes/{dishId} | N/A | {"status": "out\_of\_stock"} | {"dishId": 11, "status": "out\_of\_stock"}                 | 200 OK| 
|  POST        | /orders | N/A | {"restaurantId": 1, "items": [{"id": 10, "qty": 2}]} | {"orderId": 500, "status": "pending"}                      | 201 Created<br> 400 Bad Request| 
|  PATCH       | /orders/{id} | N/A | {"items": [{"id": 10, "qty": 1}]} | {"orderId": 500, "status": "updated"}                      | 200 OK<br> 403 Forbidden| 
|  DELETE      | /orders/{id} | N/A | N/A | {"message": "Order cancelled"}                             | 200 OK<br> 403 Forbidden| 
|  GET         | /orders/{id}/status | N/A | N/A | {"orderId": 500, "status": "in\_kitchen"}                  | 200 OK| 
|  PUT         | /orders/{id}/status | N/A | {"status": "out\_for\_delivery"} | {"orderId": 500, "new\_status": "out\_for\_delivery"}      | 200 OK | 
|  POST        | /orders/{id}/payments | N/A | {"method": "card", "token": "tok\_123"} | {"paymentId": 99, "status": "paid"}                        | 201 Created <br> 402 Payment Required| 
