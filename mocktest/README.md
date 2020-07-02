[프로그래머스 모의고사](https://programmers.co.kr/learn/courses/30/lessons/42840?language=javascript)

## 풀이
```javascript  
function solution(answers) {
    var students = [[1, 2, 3, 4, 5, 1, 2, 3, 4, 5], [2, 1, 2, 3, 2, 4, 2, 5, 2], 
                    [3, 3, 1, 1, 2, 2, 4]]
    var answer = [];
    var temp = [0, 0, 0];
       
    
    for(let i=0; i<answers.length; i++){
        if(students[0][i] == answers[i]){
            temp[0]++;
        }
        if(students[1][i] == answers[i]){
            temp[1]++;
        }
        if(students[2][i] == answers[i]){
            temp[2]++;
        }
    }
    
    var max = Math.max.apply(null, temp);
    
    for(let i=0; i<temp.length; i++){
        if(max == temp[i]){
            answer.push(i+1)
        }
    }    
    
    return answer;
}
```

## 다른 사람 풀이
```javascript
function solution(answers) {
    var answer = [];
    const man1 = [1, 2, 3, 4, 5];
    const man2 = [2, 1, 2, 3, 2, 4, 2, 5];
    const man3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5];
    let count = [0, 0, 0];

    for(let i = 0; i < answers.length; i++) {
        if(answers[i] == man1[i % man1.length]) count[0]++;
        if(answers[i] == man2[i % man2.length]) count[1]++;
        if(answers[i] == man3[i % man3.length]) count[2]++;
    }

    const max = Math.max(count[0], count[1], count[2]);
    for(let i = 0; i < count.length; i++) {
        if(max == count[i]) answer.push(i + 1);
    }

    return answer;
}
```

## 느낀점  
로직을 생각하는데는 어려움이 없었는데 다른 사람들의 풀이를 보면 수포자의 배열을 length로 나눠주던데
왜 나눠주는지 잘 모르겠다. 좀 더 찾아봐야할 것 같다. 변수를 좀 더 의미 있게 지어야겠다.
