# Ejercios Sort

## Ejercicio MergeSort
```
function mergeSort(arr){
 	if (arr.length === 1) {
    return arr
  }

	let mitad = Math.floor(arr.length/2) // 2
  let izq = arr.slice(0, mitad) // [6, 2] -> 6 -> 4
  let der = arr.slice(mitad) // [4, 1] -> 2 -> 1

  return merge (
  mergeSort(izq),
  mergeSort(der)
  )
}

function merge(izq, der) {
  result = []; // 1, 2, 4
  inIzq = 0
  inDer = 0

  while (inIzq < izq.length && inDer < der.length) {
    if (izq[inIzq] < der[inDer]){
      result.push(izq[inIzq]);
      inIzq++
    } else {
      result.push(der[inDer]);
      inDer++
    }
  }
  //return result.concat(izq).concat(der)
  return result.concat(izq.slice(inIzq).concat(der.slice(inDer)))
}
```
## Ejercicio Queue
```
function queue(arr){

	var obj = {};
  for(let i=0;i<arr.length-1;i++){
  for(let j=i+1;j<arr.length;j++){
    if(arr[i]>arr[j]){
      if (!obj[arr[i]]) {
        obj[arr[i]] = 1;
      } else {
        obj[arr[i]] += 1;
      }
      let aux=arr[i]
      arr[i]=arr[j]
      arr[j]=aux
    }
  }
 }
  var keys = Object.keys(obj)
  for (keys in obj) {
    if(obj[keys] > 2) {
    return -1
    }
  }
	return 1
}

```
