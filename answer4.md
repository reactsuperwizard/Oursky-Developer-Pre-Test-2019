// complexity O(1) f(n) = f(n - 1) + f(n - 2) 
// let's call a next biger number than m  n(th) fibonachi number
// If the 
// so n(th) fibonachi can find out similar with log(m)
// complexity is O(m);


function calcFibonachi(sum) {
  if (sum < 1) return 1;
  let first = 1;
  let second = 1;

  while (first + second <= sum) {
    const next = first + second;
    first = second;
    second = next;
  }
  return first + second;
}

function nextFibonacci(array) {
  for (let i of array) {
    console.log(calcFibonachi(i));
  }
}

nextFibonacci([1, 22, 9]);
nextFibonacci([1, 34, 9]);
