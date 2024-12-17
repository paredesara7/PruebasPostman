# PruebasPostman
Este repositorio contiene scripts de pruebas utilizando Postman para la consulta de clima a través de la API de OpenWeather. Contiene validaciones de estado, tiempo de respuesta y datos meteorológicos.

# Scripts utilizados para las pruebas:

pm.test("Estado 200, respuesta correcta", function () {
pm.response.to.have.status(200);
});

pm.test("La respuesta contiene Capiatá", function () {
pm.response.to.have.jsonBody('name', 'Capiatá');
});
pm.test("Tiempo de respuesta: 2000ms", function () {
pm.response.to.have.responseTime.below(2000);
});
pm.test("Datos de temperatura: Presente", function () {
var jsonData = pm.response.json();
pm.expect(jsonData.main.temp).to.exist;
});
