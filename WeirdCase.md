[프로그래머스 이상한 문자 만들기](https://programmers.co.kr/learn/courses/30/lessons/12930?language=javascript)

## 풀이
```javascript
function solution(s) {
    var answer = '';
    var strings = s.split(" ");
    
    for(let i=0; i<strings.length; i++){
        for(let j=0; j<strings[i].length; j++){        
            if(j%2 == 0) answer += strings[i][j].toUpperCase();
            else answer += strings[i][j].toLowerCase();        
        }
        if(i !== strings.length-1)
            answer += " ";
    }
    
    return answer;
}
```

## 풀이과정
1) input된 s를 공백을 기준으로 자른다.
2) 잘린 문자를 배열에 넣는다. -> split() 함수 

1) 배열의 길이만큼 for문을 돌린다.
2) 0 = 대문자, 홀수 = 소문자, 짝수 = 대문자  
j % 2 == 0 이면 string[i][j].toUowerCase();  
아니면 string[i][j].toUpperCase();  
3) 만든 문자열 뒤에 공백을 붙이고 answer에 넣는다. (마지막 배열에는 공백을 추가하지 않는다)
