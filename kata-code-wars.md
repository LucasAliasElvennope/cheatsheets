# ✅ 1. Somme des nombres positifs d’un tableau
But : retourner la somme des nombres positifs.

```js
function positiveSum(arr) {
  return arr.filter(num => num > 0).reduce((acc, val) => acc + val, 0);
}
.filter(num => num > 0) garde uniquement les nombres > 0.

.reduce((acc, val) => acc + val, 0) additionne tout.
```

# ✅ 2. Somme des carrés des nombres
But : élever chaque nombre au carré, puis additionner.

```js
function squareSum(numbers) {
  return numbers.reduce((acc, num) => acc + num * num, 0);
}
```
# ✅ 3. Trouver le plus petit entier dans un tableau
```js
function findSmallestInt(args) {
  return Math.min(...args);
}
```
Math.min(...args) déstructure le tableau pour comparer chaque valeur.

# ✅ 4. Somme de 1 jusqu'à num
```js
function summation(num) {
  let sum = 0;
  for (let i = 1; i <= num; i++) {
    sum += i;
  }
  return sum;
}
```
# ✅ 5. Quatre opérations mathématiques
```js
function basicOp(operation, value1, value2) {
  if (operation === '+') return value1 + value2;
  if (operation === '-') return value1 - value2;
  if (operation === '*') return value1 * value2;
  if (operation === '/') return value1 / value2;
}
```
# ✅ 6. Eau bue par Nathan
```js
function litres(time) {
  return Math.floor(time * 0.5);
}
```
Math.floor arrondit à l'entier inférieur.

# ✅ 7. Doubler un entier
```js
function doubleInteger(i) {
  return i * 2;
}
```
# ✅ 8. Compter les voyelles dans une chaîne
```js
function getCount(str) {
  return str.split('').filter(char => 'aeiou'.includes(char)).length;
}
```
# ✅ 9. Compter les moutons présents (valeurs true)
```js
function countSheeps(arrayOfSheep) {
  return arrayOfSheep.filter(Boolean).length;
}
Boolean garde les true, ignore false, null, undefined.
```
# ✅ 10. Trouver le siècle d’une année
```js
function century(year) {
  return Math.ceil(year / 100);
}
```
Math.ceil arrondit vers le haut (ex: 1705 → 18).

# ✅ 11. Plus haut et plus bas dans une chaîne
```js
function highAndLow(numbers) {
  const arr = numbers.split(' ').map(Number);
  return `${Math.max(...arr)} ${Math.min(...arr)}`;
}
```
# ✅ 12. Enlever les voyelles d'une phrase (anti-trolls)
```js
function disemvowel(str) {
  return str.replace(/[aeiou]/gi, '');
}
```
# ✅ 13. Filtrer les chaînes d’un tableau
```js
function filter_list(l) {
  return l.filter(item => typeof item === 'number');
}
```