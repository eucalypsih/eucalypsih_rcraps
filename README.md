# eucalypsih_rcraps
```javascript
let arr = ["apple", "mango", "apple",
          "orange", "mango", "mango"];

function removeDuplicates(arr) {
    return arr.filter((item,
        index) => arr.indexOf(item) === index);
}
console.log(removeDuplicates(arr));
```
```javascript
function removeDuplicates(arr) {
    const uniqueMap = {};
    const uniqueList = [];

    for (const item of arr) {
        if (!uniqueMap[item]) {
            uniqueMap[item] = true;
            uniqueList.push(item);
        }
    }
    return uniqueList;
}

const arr = ["apple", "mango", "apple", "orange", "mango", "mango"];
console.log(removeDuplicates(arr));


```
```typescript
const arr: string[] = ["apple", "mango", "apple", "orange", "mango", "mango"];

function removeDuplicates(arr: string[]): string[] {
    return arr.filter((item, index) => arr.indexOf(item) === index);
}

console.log(removeDuplicates(arr));

```
```golang
package main

import (
	"fmt"
)

func removeDuplicates(arr []string) []string {
	uniqueMap := make(map[string]bool)
	uniqueList := []string{}

	for _, item := range arr {
		if _, exists := uniqueMap[item]; !exists {
			uniqueMap[item] = true
			uniqueList = append(uniqueList, item)
		}
	}
	return uniqueList
}

func main() {
	arr := []string{"apple", "mango", "apple", "orange", "mango", "mango"}
	fmt.Println(removeDuplicates(arr))
}


```
