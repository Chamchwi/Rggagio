# 알까기오 Rggagio
# 통신 스펙
 * Rggagio의 통신은 websocket을 이용하여 json을 주고받는 형태로 작성한다.
## 게임시작
 * Server to Client : { "event" : "initialize", "my_turn" : bool,
                         "piece_info" : [{ "id" : int, "x" : int, "y" : int, "rotation" : double }] } //게임시작 초기화 작업
## 채팅
 * Client to Server : { "event" : "chat", "id" : string, "nickname" : string, "message" : string }
 * Server to Client : { "event" : "chat", "id" : string, "nickname" : string, "message" : string }
## 게임진행
 * Client to Server : { "event" : "relay", "id" : string, "piece_id" : int, "destination_x" : int, "destination_y" : int } //말 튕기기
 * Server to Client : { "event" : "relay", "id" : string, "piece_id" : int, "destination_x" : int, "destination_y" : int }
## 게임종료
 * Client to Server : { "event" : "end",  }
 * Server to Client : { "event" : "end", "win" : bool }
## 항복선언
 * Client to Server : { "event" : "surrender", "id" : string }
 * Server to Client : { "event" : "end", "win" : bool }