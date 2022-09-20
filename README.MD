# desafio-samel

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

```
#Questão 1 
vue create cantando-na-chuva

```
2 - 

```
# Questão 3
### via AXIOS

import axios from "axios";
axios
  .get("http://localhost:8000/api/users")
  .then((res) => {
          console.log(res.data)
  })
  .catch((error) => {
          console.log(error);
  });

-------------------------------------------------------

### via FETCH

created() {
  // Simple GET request using fetch
  fetch("https://api.npms.io/v2/search?q=vue")
    .then(response => response.json())
    .then(data => (this.totalVuePackages = data.total));
}
```

```
4 -
uma forma de converter callbacks para promisses é atraves da biblioteca promisefy
como mostrado no exemploa abaixo:

 const promysefy = require('promisefy-node')
 const fs = require('fs')

--- callback ---
 fs.readFile('bind.js', (err, data) => console.log(data.toString()))

--- Promise ---
const readFile = promisefy(fs.readFile)
readFile('bind.js').then((data) => console.log(data.toString()))

```
 
```
# Questão 5
numeros = [0, 1, 2, ...30]

## a)
const impares = numeros.filter((impar) => impar % 2);
console.log("\nImpares: ", impares)
## b)
const pares = numeros.filter((impar) => impar % 2 == 0)
console.log("\nPares: ", pares)
## C)
const numerosX3 = numeros.map(number => number * 3);
console.log('\nNumeros * 3: ', numerosX3)
## d)
const menorQue6 = numeros.filter((menor) => menor < 6)
console.log("\nMenor que 6: ", menorQue6)
## e)
const invertido = numeros.slice(0).reverse()
console.log("\nInvertido: ", invertido)
```