블록체인 부분 

블록체인 일반
1. 토큰과 코인의 차이는 무엇인가요? (in 이더리움)
2. 토큰 디자인에 대해서 아는대로 말해주세요.
3. 이더리움 ERC20 & ERC721 는 무슨 차이가 있나요 
4.블록체인 트릴레마(Blockchain Trilemma)란 ? 


비트코인 
1. 비트코인에서 UTXO 란 무엇인가요?
2. 비트코인에서 트랜잭션 검증은 어떻게 이루어 지나요
3. 비트코인에서 불룸필터는 왜 사용 되나요 
4. 비트코인에서 몇명 중에 몇명의 서명이 있어야 사용 할 수 있다라는 것은 어떻게 표현하나요

이더리움
1. 이더리움에서 트랜잭션 검증은 어떻게 이루어 지나요
2. 이더리움에서 블룸필터는 왜 사용 되나요
3. 이더리움에서 머클패트리샤트리란 무엇인가요
4. 이더리움에서 RLP는 무엇인가요? 왜 필요한가요? Protocol buffer 와는 어떤 차이가 있나요
5. 이더리움에서 플라즈마란 무엇인가요
6. 이더리움에서 노드디스커버리는 어떻게 이루어 지나요
7. 이더리움에서 주소를 public key 자체가 아니라, 이더리움 경우 20byte로 줄여서 사용하는 이유는 무엇인가요 장점은? 줄여진 주소를 가지고 서명을 어떻게 확인 하나요 
8. 이더리움에서 블록싱크 방식은 어떻게 되나요
9. 이더리움에서 저장용량을 줄이기 위한 prunning은 어떻게 할 수 있을까요

하이퍼레저 패브릭
1. 하이퍼레저 패브릭에서 트랜잭션 흐름을 설명해 주세요.
2. 하이퍼레저 패브릭에서 MVCC 충돌이란 무엇인가요
3. 하이퍼레저 패브릭에서 MSP 란 무엇인가요
4. 하이퍼레저 패브릭에서 Fabric-CA가 하는 역할은 무엇인가요
5. 하이퍼레저 패브릭에서 RWSet이란 무엇인가요 
6. 하이퍼레저 패브릭에서 블룸 필터는 어떻게 사용 되나요
7. 하이퍼레저 패브릭에서 ACL 은 어떤 정보를 어떻게 가져와서 적용 되나요
8. 하이퍼레저 패브릭에서 저장용량을 줄이기 위한 prunning은 어떻게 할 수 있을까요
9. 하이퍼레저 패브릭에서 Kafka 는 왜 사용 되나요? RAFT 는 왜 등장 한 걸 까요?
10. 하이퍼레저 패브릭에서 토큰은 만들 수 있나요?  FabToken 왜 만들어 졌을까요?  
11. 하이퍼레저 패브릭에서 리더피어와 앵커피어란 무엇인가요?
12. 하이퍼레저 패브릭에서 Gossip Protocol 는 왜 사용하나요?  

암호학
1.HMAC / PKI / ECDSA는 무엇인가요
2. diffie-hellman 키 교환 알고리즘은 무엇인가요? 이더리움에서는 왜 사용하나요 
3. 하이퍼레저 패브릭의 ECcert 란 무엇인가요? 패브릭에서는 왜 사용하나요 
4. 하이퍼레저 패브릭의 TCert 는 왜 없어졌고, 대체제는 무엇인가요 
5. Schnorr signature는 무엇인가요?
6. 이더리움에서 영지식증명으로 활용 할 수 있는 것은 무엇이 있을까요
7. 하이퍼레저 패브릭에서 영지식증명으로 활용 할 수 있는 것은 무엇이 있을까요
8. ECC 개인키,공개키는 수학적으로 어떻게 만들어지며 비트코인의 secp256k1 소스를 보고 함수를 설명 해 주세요.

컨센서스
1. CFT와 BFT의 차이는 무엇인가요 
2. RAFT 에서 리더 선출은 어떻게 하나요? 
3. PBFT 알고리즘은 무엇인가요
4. DPOS 알고리즘은 무엇인가요

기타

1. 하이퍼레져 패브릭 Indy 란
2. EOS에서 트랜잭션 수수료는?


블록체인 소프트웨어 일반/C++/Java/Go 

소프트웨어 일반/설계
1. inheritance보다 Composition을 사용하라는 말은 무슨 의미인가요?
2. 주로 사용하는 리팩토링 3가지를 말해 주세요.
3. 디자인패턴은 표현(구조)보다는 의도가 중요하다는 말은 무슨 의미인가요?
4. 예외에 대해서 어떻게 생각하시나요? (예외 처리에 대한 6가지 화두 참고)
5. 동기,비동기,블록,논블록은 무엇이라고 생각하나요?
6. 잠금 없는 동시성 프로그래밍이란 무엇인가요?
7. Actor 패턴과 Go언어의 CSP 모델의 차이점은 무엇인가요?
8. 공간(메모리)를 낭비해서 성능을 높이는 방식의 예를 3가지만 들어주세요.

자바
1. 자바의 메서드 인자 전달 방식과 Shallow Copy / Deep Copy 에 대해 설명 해주세요.
2. 자바의 HashMap 은 어떻게 동작하나요?
3. 자바 리플렉션은 무엇이며, 활용처가 어떤게 있을 까요?

C++
1. C++ 에서 가상함수테이블에 대해서 말해주세요
2. C++ 에서 함수포인터와 클래스멤버함수 포인터와 std::function 에 대해서 설명해주세요
3. C++ 에서 성능하락을 막기 위해 알아야 할 기본적인 것들은 무엇이 있을까요?
4. C++ 에서 성능향상을 위해서 일반적으로 할 수 있는게 무엇이 있을까요?
5. C++ 에서  STL 컨테이너의 데이터 삭제에 대해서 말해주세요
6. C++ 에서 생산자,소비자패턴중 소비자 부분의 코드입니다. 코드를 설명 해주세요

    std::unique_lock<std::mutex> ul_que_res(_mtx_recv_endorser, std::defer_lock);
    std::list<SPTR_PROPOSAL_RES> que_recv; 

    while (!_bStop) 
    { 
        ul_que_res.lock(); 
        if (_que_recv_endorser.empty()) 
            _cond_recv_endorser.wait(ul_que_res); 

        que_recv.swap(_que_recv_endorser); 
        ul_que_res.unlock(); 

        while (!que_recv.empty()) 
        { 
            res = que_recv.front(); 
            que_recv.pop_front(); ​
7. C++ 에서 std::move 와 rvalue 란 무엇인가요?
8. C++에서 메모리 풀링은 어떻게 구현하나요? (다양한 방식 중 아무거나) 
9. C++에서 unique_lock과 lock_guard의 차이점은? recursive_mutex는?  아래 코드를 설명하시요.

Buffer BufferPool::get_buf(){
   Buffer buf;
   std::unique_lock<std::mutex> ul(_mtx, std::defer_lock);

   while (buf.get() == nullptr){
    ul.lock();
    if (_pool.empty()) _cond.wait(ul);
    if (!_pool.empty())
    {
       buf = _pool.front();
      _pool.pop_front();
    }
  }

  return buf;
}
Golang
1. Go의 덕타이핑의 장,단점은 무엇인가요?
2. Go에서 고루틴&채널은 무엇인가요? 
3. Go에서 select 문은 어떻게 사용되나요? 아래 코드를 설명 해 주세요.

package main

import (
   "fmt"
   "time"
)

var scheduler chan string

func consuming (prompt string){
      fmt.Println("consuming 호출됨")
   select {
   case scheduler <- prompt:
      fmt.Println("이름을 입력받았습니다 : ", <- scheduler)
   case <-time.After(5 * time.Second):
      fmt.Println("시간이 지났습니다.")
   }
}

func producing (console chan string) {
   var name string
   fmt.Print("이름:")
   fmt.Scanln(&name)
   console <- name
}
func main() {
   console := make(chan string, 1)
   scheduler = make(chan string, 1)

   go func(){
      consuming(<-console)
   }()

   go producing(console)

   time.Sleep(100 * time.Second)
}
func (p *MsgPipeRW) WriteMsg(msg Msg) error {
  if atomic.LoadInt32(p.closed) == 0 {
    consumed := make(chan struct{}, 1)
    msg.Payload = &eofSignal{msg.Payload, msg.Size, consumed}
   select {
    case p.w <- msg:
      if msg.Size > 0 {
      // wait for payload read or discard
        select {
          case <-consumed:
          case <-p.closing:
        }
      }
      return nil
    case <-p.closing:
    }
  }
  return ErrPipeClosed
}
분산시스템
1. CAP 이론이란? 
2. consistent hashing 이란 무엇인가요?
3. Gossip Protocol 는 무엇인가요?


DB
1. 트랜잭션에서  Two Phase Commit 이란 무엇인가요?
2. WAL (write-ahead logging) 은 무엇인가요?
3. B+tree 는  무엇인가요?
4. 블록체인에서 블록저장을 위한 ON DISK 데이터 구조와 DBMS에서의 ON DISK 데이터 구조는 어떤 차이가 있을 까요?
5. LSM (log structed merge tree)은 대략 무엇인가요?
6. leveldb의 특징 및 장점은 무엇인가요? 

MQ
1. Kafka 의 브로커,토픽,파티션은 무엇인가요?
2. Kafka 에서 Zookeeper 는 무엇이고 어떤 역할을 담당하나요?

네트워킹 / 소켓
1. 멀티쓰레드 방식과 Select or ePoll 방식의 소켓통신 차이점은 무엇인가요?
2. 소켓통신에서 가변 read 버퍼와 고정 read 버퍼 각각의 장,단점은? 가변버퍼시 메모리 풀링 방식은? 
3. 소켓통신에서 타임아웃은 무엇이고 Nagle 알고리즘은 무엇인가요?
4. 소켓통신상 SSL/TLS flow를 말해주세요
5. React 방식과 Proact 방식의 차이점은 무엇인가요?  (in POSA2) 

Reactor

Event Handling

Allows event-driven applications to demultiplex and dispatch service requests that are delivered to an application from one or more clients.

Proactor

Event Handling

Allows event-driven applications to efficiently demultiplex and dispatch service requests triggered by the completion of asynchronous operations, to achieve the performance benefits of concurrency without incurring certain of its liabilities.

6. NAT 와 UPnP 는 무엇인가요?


인프라 & 데브옵스 아키텍쳐 

도커 + 쿠버네이트등 컨테이너화
빌드자동화
테스트자동화
디플로이자동화
서비스관리 자동화 (앤서블등) 
이슈등록자동화
네트워킹 인프라에 대한 이해 
수직 / 수평 분활에 대한 이해 
무정지 시스템 이해 및 구축 (무정지 리소스 증축등) 


출처: https://hamait.tistory.com/1054?fbclid=IwAR3evELtDtaaXqHWpaI8z3C-ALIwXl_y1YGRsNJO8efILpNDXAOF8CJp7EY [HAMA 블로그]
