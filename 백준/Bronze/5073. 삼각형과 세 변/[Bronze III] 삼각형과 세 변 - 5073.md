# [Bronze III] 삼각형과 세 변 - 5073 

[문제 링크](https://www.acmicpc.net/problem/5073) 

### 분류

수학, 구현, 기하학

### 문제 설명

<p>삼각형의 세 변의 길이가 주어질 때 변의 길이에 따라 다음과 같이 정의한다.</p>

<ul>
	<li>Equilateral :  세 변의 길이가 모두 같은 경우</li>
	<li>Isosceles : 두 변의 길이만 같은 경우</li>
	<li>Scalene : 세 변의 길이가 모두 다른 경우</li>
</ul>

<p>단 주어진 세 변의 길이가 삼각형의 조건을 만족하지 못하는 경우에는 "Invalid" 를 출력한다. 예를 들어 6, 3, 2가 이 경우에 해당한다. 가장 긴 변의 길이보다 나머지 두 변의 길이의 합이 길지 않으면 삼각형의 조건을 만족하지 못한다.</p>

<p>세 변의 길이가 주어질 때 위 정의에 따른 결과를 출력하시오.</p>

### 입력 

 <p>각 줄에는 1,000을 넘지 않는 양의 정수 3개가 입력된다. 마지막 줄은 0 0 0이며 이 줄은 계산하지 않는다.</p>

### 출력 

 <p>각 입력에 맞는 결과 (Equilateral, Isosceles, Scalene, Invalid) 를 출력하시오.</p>



#  🚀  오답노트 

```diff
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while(true){
            int a = sc.nextInt();
            int b = sc.nextInt();
            int c = sc.nextInt();

            int[] arr = {a, b, c};

-            Arrays.sort(arr);
-
-            // for(int n : arr){
-                // System.out.println(n);
-            // }
-            if (arr[2] >= arr[0] + arr[1]){
+            if (a == 0 && b == 0 && c == 0){
+                break;
+            }
+                
+            if ((a + b <= c) || (b + c <= a) || (a + c <= b)){
                System.out.println("Invalid");
-                
-                if ((a == b) && (b == c) && (a == c)){
-                    System.out.println("Equilateral");
-                }
-                else if ((a == b) || (b == c)){
-                    System.out.println("Isosceles");
-                }
-                else if ((a != b) && (b != c) && (a != c)){
-                    System.out.println("Scalene");
-                }
            }
-
-            if(arr[0] == 0){
-                break;
+            else if ((a == b) && (b == c)){
+                System.out.println("Equilateral");
            }
+            else if ((a == b) || (b == c) || (a == c)){
+                System.out.println("Isosceles");
+            }
+            else if ((a != b) && (b != c) && (a != c)){
+                System.out.println("Scalene");
+            }
            sc.nextLine();
        }

    }
}

```

# 💻 코드 리뷰
- 처음에는 정렬한 뒤에 max를 구해서 나머지 길이의 합보다 작으면 Invalid 출력을 했으나,
- 이를 큰 if문으로 먼저 시작했고, 정렬을 아예 빼고 조건식을 수정했다. 



 ## 🏆 메모 

