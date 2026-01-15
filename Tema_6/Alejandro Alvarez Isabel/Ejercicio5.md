# Ejercicio 5: Hunde la flota 

| Método HTTP | URI                 | Query Params  | Cuerpo de la Petición                                             | Cuerpo de la Respuesta                                                  | Códigos de Respuesta                          |
|-------------|---------------------|---------------|-------------------------------------------------------------------|-------------------------------------------------------------------------|-----------------------------------------------|
| POST | /users | N/A | {"name": "Capitan", "isGuest": false}                           | {"userId": 501, "token": "abc-123"} | 201 Created                                   |
| GET | /users/{userId} | N/A | N/A                                                               | {"userId": 501, "stats": {"wins": 10, "games": 25}} | 200 OK                                        |
| POST | /games | N/A | {"player1Id": 501, "player2Id": 502}                            | {"gameId": "G99", "status": "setup"} | 201 Created                                   |
| GET | /games/{gameId} | N/A | N/A                                                               | {"gameId": "G99", "players": [...], "winner": null, "status": "active"} | 200 OK                                        |
| PATCH | /games/{gameId} | N/A | {"status": "started"}                                           | {"gameId": "G99", "status": "started"} | 200 OK <br> 422 Unprocessable                 |
| POST | /games/{gameId}/players/{userId}/ships | N/A | {"type": "destroyer", "size": 3, "coords": [[0,0],[0,1],[0,2]]} | {"shipId": 1, "valid": true} | 201 Created <br> 400 Bad Request                  |
| DELETE | /games/{gameId}/players/{userId}/ships/{shipId} | N/A | N/A                                                               | {"message": "Ship removed"} | 200 OK                                        |
| GET | /games/{gameId}/players/{userId}/ships | N/A | N/A                                                               | {"ships": [{"id": 1, "coords": [...]}]} | 200 OK                                        |
| POST | /games/{gameId}/players/{userId}/shots | N/A | {"x": 5, "y": 5}                                                | {"result": "hit", "sunk": false, "nextTurn": 502} | 201 Created<br> 403 Forbidden |
| DELETE | /games/{gameId} | N/A | N/A                                                               | {"message": "Game deleted"} | 200 OK                                        |