Assignment is to calculate Receptive Field and compare with paper mentioned below.

https://arxiv.org/pdf/1409.4842.pdf 
They mention on page 6, that the RF is 224x224. 
Use the formulas above and show the calculations


| **N-in** | **k** | **p** | **s** | **N-out** | **J-in** | **J-out** | **R-in** | **R-out** |
| -------- | ----- | ----- | ----- | --------- | -------- | --------- | -------- | --------- |
| 224      | 7     | 3     | 2     | 112       | 1        | 2         | 1        | 7         |
| 112      | 3     | 1     | 2     | 56        | 2        | 4         | 7        | 11        |
| 56       | 3     | 1     | 1     | 56        | 4        | 4         | 11       | 19        |
| 56       | 3     | 1     | 2     | 28        | 4        | 8         | 19       | 27        |
| 28       | 5     | 2     | 1     | 28        | 8        | 8         | 27       | 59        |
| 28       | 5     | 2     | 1     | 28        | 8        | 8         | 59       | 91        |
| 28       | 3     | 1     | 2     | 14        | 8        | 16        | 91       | 107       |
| 14       | 5     | 2     | 1     | 14        | 16       | 16        | 107      | 171       |
| 14       | 5     | 2     | 1     | 14        | 16       | 16        | 171      | 235       |   **OUTPUT 1**
| 14       | 5     | 2     | 1     | 14        | 16       | 16        | 235      | 299       |
| 14       | 5     | 2     | 1     | 14        | 16       | 16        | 299      | 363       |
| 14       | 5     | 2     | 1     | 14        | 16       | 16        | 363      | 427       |   **OUTPUT 2**
| 14       | 3     | 1     | 2     | 7         | 16       | 32        | 427      | 459       |
| 7        | 5     | 2     | 1     | 7         | 32       | 32        | 459      | 587       |
| 7        | 5     | 2     | 1     | 7         | 32       | 32        | 587      | 715       |
| 7        | 7     | 0     | 1     | 1         | 32       | 32        | 715      | 907       |   **OUTPUT 3**

 

Model has three outputs, RF at each of these out puts are mentioned below

Output1  =  235 x 235

Output2  =  427 x 427

Output3  =  907 x 907
