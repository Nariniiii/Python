# Python
문제:
오차 값을 입력 받아서, 특정 항까지 계산한 π값과 그 다음 항까지 계산한 π값의 차이 값이
    [입력 받은] 오차 값보다 작은 경우에 해당하는 항의 [근사값] π을 출력하는 프로그램

    ex1) 오차값을 실수로 입력하세요: 0.01
    3.1365926848388161

    ex2) 오차값을 실수로 입력하세요: 0.001
    3.1410926536210413


제가 접근한 방법:
일단 문제가 뭔지 이해했다고 가정하고 설명할게요...!

π=  4/1 - 4/3+  4/5-  4/7+  4/9-  4/11+ ⋯

저는 일단 이거를 보면서 어떻게 해야 각 항들을 계산할 수 있을지를 생각을 해봤어요. 


첫번째 항은 4/1
두번째항까지 계산한 거는 4/1 - 4/3
세번째항까지 계산한 거 4/1 - 4/3+  4/5
네번째 항까지 계산한 거  4/1 - 4/3+  4/5-  4/7


이거를 보면서 규칙을 잡았어요. 

첫번째 규칙:  4/? 여기서 ?부분이 1,3,5,7,9,11,... 이런 식으로 '1부터 시작해서 2씩 증가'하네.
두번째 규칙: 각 항을 더하는데 '짝수번째' 항에는 -1을 곱해서 더하는 구나. (저번 퀴즈 마지막 문제처럼)


그래서 반복문을 통해서 일단 네번째 항까지 계산하는 코드 먼저 작성해봐야겠다고 생각했어요.

  num = 1      #num = 1,3,5,7.... 
  PI = 0    #계산한 최종 값이 들어가는 변수 
  count = 1   #짝수번째 항인지 홀수번째 항인지 계산하는 데 쓰는변수 

  while num <= 7: 
    hang = 4/num     #hang: 각 항을 계산하는 변수 
    if count % 2 == 0: 
      hang = hang * (-1)     #짝수번째 항이면 -1을 곱한다. 
    PI = PI + num 

  num = num + 2 
  count = count + 1 
  
이렇게 코드를 짜면
