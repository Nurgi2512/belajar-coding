# belajar-coding
Shifting Members of an Array, Segitiga Paskal, Jarak maksimal antara 3 titik

## Shifting Members of an Array
Pada pertanyaan ini, kita ingin menggeser array ke kanan. seberapa banyak?
Tergantung dari input

##### Example 1:
```Python
array = [1,2,3,4,5]
steps = 3

Kita harus menggeser array 3 langkah ke kanan.
- Original array = [1,2,3,4,5]
- Step 1 = [5,1,2,3,4]
- Step 2 = [4,5,1,2,3]
- Step 3 = [3,4,5,1,2]

Answer = [3,4,5,1,2]
```
##### Example 2:
```Python
array = [1,2,3]
steps = 5

Kita harus menggeser array 3 langkah ke kanan.

- Original array = [1,2,3]
- Step 1 = [3,1,2]
- Step 2 = [2,3,1]
- Step 3 = [1,2,3]
- Step 4 = [3,1,2]
- Step 5 = [2,3,1]

Answer = [2,3,1]
```
### Write your function here ###
```Python
def shift(array, steps):
    for i in range(steps):
        index = len(array) - 1  # Index diisi paling kanan
        nilai = array[index]  # Nilai elemen paling kanan disimpan

        while index > 0:
            array[index] = array[index - 1]
            index -= 1

        array[0] = nilai

    return array
shift([1,2,3,4,5],4)

# Expected Output: [2, 3, 4, 5, 1]
```

# Segitiga Paskal
Kita akan membuat segitiga paskal sebanyak n-baris. fungsi yang dibuat harus bernama ```pascal```. <br>
Apabila belum mengetahui apa itu segitiga paskal, <br>
silahkan lihat video: https://www.youtube.com/watch?v=1D3KsvfB8b0 dan baca https://www.mathsisfun.com/pascals-triangle.html
```Python
def pascal(input):
    if input == 0:
        array = [1]
    elif input == 1:
        array = [1, 1]
    else:
        arraya = [1, 1]

        for z in range(1, input):
            arrayb = [1]

            for x in range(len(arraya) - 1):
                arrayb.append(arraya[x] + arraya[x + 1])

            arrayb.append(1)
            arraya = arrayb

        array = arraya

    return array

pascal(4)

pascal(3)
```

## Jarak maksimal antara 3 titik

Terdapat 3 koordinat, tentukan jarak antar 2 titik mana yang memiliki jarak terjauh, dan berikan output jarak kedua titik tersebut. fungsi yang kita buat harus bernama ```max_ditance```. titik koordinat pertama disebut 'A', titik kedua disebut'B', dan titik ketiga disebut 'C'  

``` Python
def max_distance(A,B,C):
    return
import math

def distance(x1_y1, x2_y2):
    return math.sqrt((x1_y1[0] - x2_y2[0])**2 + (x1_y1[1] - x2_y2[1])**2)

def max_distance(A, B, C):
    distance_AB = distance(A, B)
    distance_BC = distance(B, C)
    distance_AC = distance(A, C)

    max_dist = max(distance_AB, distance_BC, distance_AC)

    if max_dist == distance_AB:
        return f"The point A,B are furthest apart with distance {max_dist:.1f}"
    elif max_dist == distance_BC:
        return f"The point B,C are furthest apart with distance {max_dist:.1f}"
    else:
        return f"The point A,C are furthest apart with distance {max_dist:.1f}"

# Example
A = [1, 2]
B = [10, -10]
C = [-3, 5]

result = max_distance(A, B, C)
print(result)
```



