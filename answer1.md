// complexity O(Array1.length + Array2.length) = O(n)

function isSubset(Array1, Array2) {
	let keyZmap = {};
	for(const i of Array1 ) {
		keyZmap[i] = true;		
	}
	
	for(const i of Array2) {
		if(!(i in keyZmap)) return false;
	}
	return true;
}

function print(res) {
	console.log(res);
}
let res = '';

res = isSubset(['A','B','C','D','E'], ['A','E','D']);
print(res);


res = isSubset(['A','B','C','D','E'], ['A','D','Z']);
print(res);

res = isSubset(['A','D','E'], ['A','A','D','E']);
print(res);
