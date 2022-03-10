# 아카라이브 API

이 라이브러리는 아카라이브에 접근할 수 있게 해주는 API입니다.


# 예시

    import arcalive
    import json
    
    api = arcalive.ArcaAPI()
    info = (api.get_channel_info('programmers'))
    print(json.dumps(info, sort_keys=True, indent=4, ensure_ascii=False))

**결과:**

    {
        "category": [
            {
                "display_name": "공지사항",
                "name": "%EA%B3%B5%EC%A7%80%EC%82%AC%ED%95%AD"
            },
            {
                "display_name": "하드웨어",
                "name": "%ED%95%98%EB%93%9C%EC%9B%A8%EC%96%B4"
            },
            {
                "display_name": "보안",
                "name": "%EB%B3%B4%EC%95%88"
            },
            {
                "display_name": "윈도우",
                "name": "%EC%9C%88%EB%8F%84%EC%9A%B0"
            },
            {
                "display_name": "리눅스",
                "name": "%EB%A6%AC%EB%88%85%EC%8A%A4"
            },
            {
                "display_name": "게임 제작",
                "name": "%EA%B2%8C%EC%9E%84%20%EC%A0%9C%EC%9E%91"
            },
            {
                "display_name": "C",
                "name": "C"
            },
            {
                "display_name": "Java",
                "name": "Java"
            },
            {
                "display_name": "Python",
                "name": "Python"
            },
            {
                "display_name": "그외 언어",
                "name": "%EC%BD%94%EB%94%A9"
            },
            {
                "display_name": "웹",
                "name": "%EC%9B%B9"
            },
            {
                "display_name": "임베디드",
                "name": "%EC%9E%84%EB%B2%A0%EB%94%94%EB%93%9C"
            },
            {
                "display_name": "조언",
                "name": "%EC%A1%B0%EC%96%B8"
            },
            {
                "display_name": "질문",
                "name": "%EC%A7%88%EB%AC%B8"
            }
        ],
        "juddak": "@허언채팅",
        "name": "컴퓨터공학 채널",
        "subscribe": 1646
    }



## DOCS

### ArcaAPI.\_\_init\_\_(**kwarg)

| | |
|--|--|
| **kwarg | 매 request 마다 사용할 arg |

### ArcaAPI.login(id, password)

| | |
|--|--|
| id | 유저의 ID |
| password | 유저의 비밀번호 |

아카라이브에 로그인합니다.
댓글 작성, 게시물 작성, 권한이 필요한 행동이 할때 먼저 로그인이 필요합니다.

### ArcaAPI.delete_post(id)

| | |
|--|--|
| id | 게시물의 ID |

게시물을 삭제합니다.

### ArcaAPI.delete_comment(pid, id)

| | |
|--|--|
| pid | 게시물의 ID |
| id | 댓글의 ID |

댓글을 삭제합니다.

### ArcaAPI.post_article(channel, name, content, category=None, copy_humor=False, agree_prevent_delete=False)

| | |
|--|--|
| channel | 채널의 ID |
| name | 게시물 이름 |
| content  | 게시물 content (HTML) |
| category | 카테고리 name |
| copy_humor | 유머 채널 복사 여부 |
| agree_prevent_delete | 자삭 방지 게시물 동의 여부 |

게시물을 업로드합니다

### ArcaAPI.get_channel_info(channel)

| | |
|--|--|
| channel | 채널의 ID |

채널의 정보를 dic으로 return 합니다.

### ArcaAPI.get_channel_article(channel, page=1, best=False, category=None, cut_rate=None, sort=None)

| | |
|--|--|
| channel | 채널의 ID |
| page | 게시물 페이지 |
| best | 개념글 유무 |
| category | 카테고리 |
| cut_rate | 추천컷 |
| sort | 정렬 |
| search | 검색어 |
| search_target | 검색 종류 |

채널의 게시물과 공지의 리스트를 return 합니다.

### ArcaAPI.get_article(id)
| | |
|--|--|
| id | 게시물의 ID |

게시물의 정보, 내용, 댓글을 return 합니다.

### ArcaAPI.post_comment(id, message, reply_to=None)
| | |
|--|--|
| id | 게시물의 ID |
| message | 댓글 내용 |
| reply_to | 덧글을 달 댓글 ID |

댓글을 답니다.

### ArcaAPI.like(id, dislike=False)
| | |
|--|--|
| id | 게시물의 ID |
| dislike | 비추천 여부 |~~~~

추천/비추천 합니다.

### ArcaAPI.get_cookie()
| | |
|--|--|
| | |

쿠키를 dict 형태로 return합니다.

### ArcaAPI.get_notification()
| | |
|--|--|
| | |

알람을 return합니다.