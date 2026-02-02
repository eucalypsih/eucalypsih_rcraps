```javascript
let arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
function removeDuplicates(arr) {
    return arr.filter((item) => item % 2);
}
console.log(removeDuplicates(arr));
```
```typescript
let arr: number[] = [1, 2, 3, 4, 5, 6, 7, 8, 9];
function removeDuplicates(arr: number[]): number[] {
    return arr.filter((item: number) => item % 2);
}
console.log(removeDuplicates(arr));
```
```kotlin
fun removeDuplicates(arr: IntArray): IntArray {
    val result = mutableListOf<Int>()
    for (item in arr) {
        if (item % 2 != 0) {
            result.add(item)
        }
    }
    return result.toIntArray()
}

fun main() {
    val arr = intArrayOf(1, 2, 3, 4, 5, 6, 7, 8, 9)
    println(removeDuplicates(arr).joinToString(", "))
}


```
```golang
package main

import (
	"fmt"
)

func removeDuplicates(arr []int) []int {
	var result []int
	for _, item := range arr {
		if item%2 != 0 {
			result = append(result, item)
		}
	}
	return result
}

func main() {
	arr := []int{1, 2, 3, 4, 5, 6, 7, 8, 9}
	fmt.Println(removeDuplicates(arr))
}

```
```c++
#include <iostream>
#include <vector>

std::vector<int> removeDuplicates(const std::vector<int>& arr) {
    std::vector<int> result;
    for (const auto& item : arr) {
        if (item % 2 != 0) {
            result.push_back(item);
        }
    }
    return result;
}

int main() {
    std::vector<int> arr = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    std::vector<int> result = removeDuplicates(arr);
    for (const auto& item : result) {
        std::cout << item << " ";
    }
    return 0;
}

```
```c
#include <stdio.h>
#include <stdlib.h>

int* removeDuplicates(int* arr, int size, int* resultSize) {
    int* result = (int*)malloc(size * sizeof(int));
    *resultSize = 0;
    for (int i = 0; i < size; i++) {
        int item = arr[i];
        if (item % 2 != 0) {
            result[(*resultSize)++] = item;
        }
    }
    return result;
}

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
    int size = sizeof(arr) / sizeof(arr[0]);
    int resultSize;
    int* result = removeDuplicates(arr, size, &resultSize);
    
    for (int i = 0; i < resultSize; i++) {
        printf("%d ", result[i]);
    }
    free(result);
    return 0;
}


```
```assembly
section .data
    arr db 1, 2, 3, 4, 5, 6, 7, 8, 9
    arr_len equ 9
    result resb arr_len

section .bss
    result_len resb 1

section .text
    global _start

_start:
    mov ecx, 0          ; index for arr
    mov ebx, 0          ; index for result
    mov byte [result_len], 0

.loop:
    cmp ecx, arr_len
    jge .done           ; if index >= arr_len, exit loop

    mov al, [arr + ecx] ; load item from arr
    test al, 1          ; check if item is odd
    jz .next            ; if even, skip

    mov [result + ebx], al ; append item to result
    inc ebx             ; increment result index
    inc byte [result_len] ; increment result length

.next:
    inc ecx             ; increment arr index
    jmp .loop           ; repeat loop

.done:
    ; Here you would typically call a print function to display the result
    ; For simplicity, we will just exit
    mov eax, 60        ; syscall: exit
    xor edi, edi       ; status: 0
    syscall

```
