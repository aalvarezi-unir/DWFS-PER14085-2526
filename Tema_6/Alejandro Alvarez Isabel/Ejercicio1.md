
| Método HTTP | URI                 | Query Params  | Cuerpo de la Petición      | Cuerpo de la Respuesta                                                                        | Códigos de Respuesta                                    |
|-------------|---------------------|---------------|----------------------------|-----------------------------------------------------------------------------------------------|---------------------------------------------------------|
| POST        | /calculations/sum   | N/A           | {"values": [2, 2, 2]}      | {"id": 1, "result": 6, "op": "sum"}                                                           | 200 OK<br/>400 Bad Request   |
| POST        | /calculations/sub   | N/A           | {"values": [10, 2, 3]}     | {"id": 2, "result": 5, "op": "sub"}                                                           | 201 Created<br/>400 Bad Request |
| POST        | /calculations/mul   | N/A           | {"a": 2, "b": 2}           | {"id": 3, "result": 4, "op": "mul"}                                                           | 200 OK<br/>404 Not Found     |
| POST        | /calculations/div   | N/A           | {"a": 10, "b": 2}          | {"id": 4, "result": 5, "op": "div"}                                                           | 200 OK<br/>404 Not Found     |
| POST        | /calculations/root  | N/A           | {"base": 8, "index": 3}    | {"id": 5, "result": 2, "op": "root"}                                                          | 200 OK<br/>400 Bad Request<br/>404 Not Found|
| POST        | /calculations/power | N/A           | {"base": 2, "exponent": 2} | {"id": 6, "result": 4, "op": "power"}                                                         | 202 Accepted<br/>404 Not Found   |
| GET         | /calculations       | limit, offset | N/A                        |  {"history": [{"id": 1, "result": 6}, {"id": 2, "result": 5}]}                                | 200 OK<br/>400 Bad Request<br/>404 Not Found|
| GET         | /calculations/{id}  | N/A           | N/A                        | {"id": 1, "op": "sum", "values": [2, 2, 2], "result": 6, "timestamp": "2024-05-20T10:00:00Z"} | 202 Accepted<br/>404 Not Found   |
| DELETE      | /calculations       | N/A           | N/A                        | {"message": "Memory cleared successfully"}                                                    | 202 Accepted<br/>404 Not Found <br/>500 Internal Server Error   |


