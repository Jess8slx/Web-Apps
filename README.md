Primera Seccion
1.Utilice el procedimiento visto en clase para la conversión de los siguientes números
decimales a binarios:

a. 7

7/2= 3 Residuo 1
3/2= 1 Residuo 1
1/2= 0 Residuo 1

R// 111

b. 45

45/2= 22 Residuo 1
22/2= 11 Residuo 0
11/2= 5  Residuo 1
5/2= 2   Residuo 1
2/2= 1   Residuo 0
1/2= 0   Residuo 1

R// 101101

c. 123

123/2= 61 Residuo 1
61/2= 30  Residuo 1
30/2= 15  Residuo 0
15/2= 7   Residuo 1
7/2= 3    Residuo 1
3/2= 1    Residuo 1
1/2= 0    Residuo 1

R// 1111011

d. 8.75

8/2= 4 Residuo 0
4/2= 2 Residuo 0
2/2= 1 Residuo 0
1/2= 0 Residuo 1

0.75*2= 1.5
0.5*2=  1.0

R// 1000.11

e. -18

18/2= 9 Residuo 0
9/2= 4  Residuo 1
4/2= 2  Residuo 0
2/2= 1  Residuo 0
1/2= 0  Residuo 1
0001 0010


-1110 1101
+0000 0001 /Se suma uno para obtener el complemento a dos
R// 1110 1110


/*Ejercicio 1: Sistema de Evaluación de Riesgo
Cree una función que evalúe el nivel de riesgo de un cliente bancario basado en varios factores.
• Defina la función evaluateRisk(income, hasLoans, latePayments, isStudent):
o Un cliente es considerado de alto riesgo si:
§ Tiene ingresos menores a $20,000 y más de 3 pagos atrasados.
§ O Aene préstamos acAvos y es estudiante.
o Un cliente es considerado de riesgo moderado si:
§ Tiene ingresos entre $20,000 y $50,000, y no Aene más de 2 pagos
atrasados.
§ O si Aene préstamos pero no es estudiante.
o Si no cumple ninguna de estas condiciones, se considera de bajo riesgo.
• Retorne el nivel de riesgo como un string: 'High', 'Moderate' o 'Low'.
• Por ejemplo, el uso de la función sería:
o console.log(evaluateRisk(15000, true, 4, true)); // "High"*/

function evaluateRisk(income, hasLoans, latePayments, isStudent) {
    if ((income < 20000 && latePayments > 3) || (hasLoans && isStudent)) {
        return 'High';
    } else if ((income >= 20000 && income <= 50000 && latePayments <= 2) || (hasLoans && !isStudent)) {
        return 'Moderate';
    } else {
        return 'Low';
    }   
}
console.log(evaluateRisk(5000, true, 5, true)); // "High"
console.log(evaluateRisk(30000, true, 1, false)); // "Moderate"
console.log(evaluateRisk(60000, false, 0, false)); // "Low"

//Explicacion: Creamos la funcion evaluarteRisk, siguiendo las condiciones dadas en el ejercicio, utilizando operadores logicos ( && || >=) para evaluar las condiciones y retornar el nivel de riesgo correspondiente.

/* Ejercicio 2: Motor de Recomendación de Productos
Diseñe una función para recomendar productos a un usuario basado en varios factores.
• Cree una función recommendProduct(age, isMember, purchaseHistory):
o Un producto de alta tecnología se recomienda si:
§ La persona es miembro y ha comprado al menos 5 productos tecnológicos
antes.
§ O si la persona Aene entre 18 y 30 años y ha comprado 2 o más productos
de moda.
o Un producto de moda se recomienda si:
§ La persona no es miembro, pero ha comprado al menos 3 productos antes.
§ O si Aene entre 25 y 40 años.
§ En cualquier otro caso, recomienda un producto genérico.
• purchaseHistory es un objeto con la canAdad de productos comprados por categoría: {
tech: number, fashion: number, other: number }.
• Por ejemplo, el uso de la función sería:
o console.log(recommendProduct(22, true, { tech: 6, fashion: 1, other: 2 })); //
"High-Tech Product"*/

function recommendProduct(age, isMember, purchaseHistory) {
    if ((isMember && purchaseHistory.tech >= 5) || (age >= 18 && age <= 30 && purchaseHistory.fashion >= 2)) {
        return 'High-Tech Product';
    } else if ((!isMember && (purchaseHistory.tech + purchaseHistory.fashion + purchaseHistory.other) >= 3) || (age >= 25 && age <= 40)) {
        return 'Fashion Product';
    } else {
        return 'Generic Product';
    }
}

console.log(recommendProduct(22, true, { tech: 6, fashion: 1, other: 2 })); // "High-Tech Product"
console.log(recommendProduct(35, false, { tech: 1, fashion: 1, other: 2 })); // "Fashion Product"
console.log(recommendProduct(45, false, { tech: 0, fashion: 1, other: 1 })); // "Generic Product"

//Explicacion: Creamos la funcion recommendProduct, siguiendo las condiciones dadas en el ejercicio, utilizando operadores logicos ( && || >=) para evaluar las condiciones y retornar el tipo de producto recomendado. 
//La diferencia con el ejercicio anterior es que aqui usamos un objeto para el historial de compras, accediendo a sus propiedades con la notacion de punto y agregando los datos desde el console.log.
//Agregamos la infomacion dentro de corchetes {} para definir el objeto y sus propiedades.

