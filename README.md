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
```rust
use std::collections::HashMap;

fn remove_duplicates(arr: Vec<&str>) -> Vec<&str> {
    let mut unique_map = HashMap::new();
    let mut unique_list = Vec::new();

    for &item in &arr {
        if !unique_map.contains_key(item) {
            unique_map.insert(item, true);
            unique_list.push(item);
        }
    }
    unique_list
}

fn main() {
    let arr = vec!["apple", "mango", "apple", "orange", "mango", "mango"];
    println!("{:?}", remove_duplicates(arr));
}

```
```c++
#include <iostream>
#include <vector>
#include <unordered_map>
#include <string>

std::vector<std::string> removeDuplicates(const std::vector<std::string>& arr) {
    std::unordered_map<std::string, bool> uniqueMap;
    std::vector<std::string> uniqueList;

    for (const auto& item : arr) {
        if (uniqueMap.find(item) == uniqueMap.end()) {
            uniqueMap[item] = true;
            uniqueList.push_back(item);
        }
    }
    return uniqueList;
}

int main() {
    std::vector<std::string> arr = {"apple", "mango", "apple", "orange", "mango", "mango"};
    std::vector<std::string> result = removeDuplicates(arr);
    
    for (const auto& item : result) {
        std::cout << item << " ";
    }
    std::cout << std::endl;

    return 0;
}
```
