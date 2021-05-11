# Research And Develop - Kakao buffalo & Full text search
본 저장소는 앞으로 있을 프로젝트에 사용될 기능들에 대한 R&D를 진행하는 저장소이다.
기본적으로 `검색`, `추천` 에 그 목적을 두고 R&D를 진행한다.

`추천`으로는 Kakao Buffalo 를 사용해보고, Movie Lens의 데이터셋을 쪼개서 검증하는 방식을 진행해 본다.
그 후 기회가 된다면 사내 Log Data를 Parsing해서 샘플 돌려본다.

`검색`으로는 우선 MySQL Full Text Search를 이용해보고, 될 수 있으면 Elastic Search와 같은것을 사용해 보는것이 목적이다.

## Kakao Buffalo
기본적으로 Kakao Buffalo를 Docker로 말아서 돌린다.
Data는 buffalo 에 들어있는 public 데이터인 movice lens의 영화 평점 데이터(100k)를 사용한다.

### Data Formats
#### Main
```
(User ID) (Item ID) (Value)
1 1 5
2 4 3
...
```
#### UID
```
(Value)
심대수
심성수
...
```
#### IID
```
(Item Value)
0.Toy_Story_(1995)
1.GoldenEye_(1995)
2.Four_Rooms_(1995)
3.Get_Shorty_(1995)
4.Copycat_(1995)
...
```

### 생각해볼점
1. 어떻게 로그를 저장하는가?
2. 어디에 로그를 저장하는가?
3. 어떻게 로그를 가져올 것인가?
4. 결과를 어떻게 전달할 것인가? (어떻게 기존 서비스와 연동할 것인가?)
