
let cache = {}
let MaxSizeOfCache = 100;
function get(key) {
	if (key in cache) {
		cache[key].last_access_time = Date.now();
		return cache[key].value;
	} else return -1;
}

function put(key, value, weight) {
	let inputEle = {
		value: value,
		weight: weight,
		last_access_time: now()
	}

	if (cache.length < MaxSizeOfCache) {
		cache[key] = inputEle;
	} else {
		let isFirstObj = true;
		let maxWeight;
		let canidx;

		for (let i in cache) {
			let curObj = cache[i];
			let curWei = curObj.weight / Math.log(Date.now() - curObj.last_access_time);
			if (isFirstObj || maxWeight > curWei) {
				canidx = i;
				maxWeight = curWei;
				isFirstObj = false;
			}
		}

		delete cache[canidx];
		// cache.splice(canidx, 1);
		cache[key] = inputEle;
	}
}
put(10, 10, 10);
console.log(get(10));
