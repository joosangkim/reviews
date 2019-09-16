## Medium Openbook Interview[Blockchain]
### 블록체인 일반
1. 토큰과 코인의 차이는 무엇인가요? (in 이더리움)
  * 코인 : 메인넷을 보유하고 있는 블록체인 네트워크에서 교환되는 암호화폐
  * 코인 : 메인넷 을 보유하고 있지 않은 암호화폐
2. 토큰 디자인에 대해서 아는대로 말해주세요.
3. 이더리움 ERC20 & ERC721 는 무슨 차이가 있나요 
4. 블록체인 트릴레마(Blockchain Trilemma)란 ? 


### 비트코인 
1. 비트코인에서 UTXO 란 무엇인가요?
  * UTXO는 account 로 in/out된 비트코인들의 덩어리이다. 즉, 사용되지 않고 account에 남아있는 토큰의 덩어리들이다. 비트코인에서 토큰 전송 시, 전송하고자 하는 UTXO의 덩어리들의 합을 전송하게 된다. 
2. 비트코인에서 트랜잭션 검증은 어떻게 이루어 지나요
3. 비트코인에서 불룸필터는 왜 사용 되나요 
4. 비트코인에서 몇명 중에 몇명의 서명이 있어야 사용 할 수 있다라는 것은 어떻게 표현하나요

### 이더리움
1. 이더리움에서 트랜잭션 검증은 어떻게 이루어 지나요
2. 이더리움에서 블룸필터는 왜 사용 되나요
3. 이더리움에서 머클패트리샤트리란 무엇인가요
4. 이더리움에서 RLP는 무엇인가요? 왜 필요한가요? Protocol buffer 와는 어떤 차이가 있나요
5. 이더리움에서 플라즈마란 무엇인가요
6. 이더리움에서 노드디스커버리는 어떻게 이루어 지나요
7. 이더리움에서 주소를 public key 자체가 아니라, 이더리움 경우 20byte로 줄여서 사용하는 이유는 무엇인가요 장점은? 줄여진 주소를 가지고 서명을 어떻게 확인 하나요 
8. 이더리움에서 블록싱크 방식은 어떻게 되나요
9. 이더리움에서 저장용량을 줄이기 위한 prunning은 어떻게 할 수 있을까요

### 하이퍼레저 패브릭
1. 하이퍼레저 패브릭에서 트랜잭션 흐름을 설명해 주세요.
  * 하이퍼레저(이하 HLF)에서의 트랜잭션은 query / invoke 두 가지로 나눌수 있다. 
    + query: HLF 클라이언트에서 peer 로 원장 데이터를 조회하기 위한 트랜잭션이다. 트랜잭션 흐름은 client(sdk) -> peer -> client(sdk) 
    + invoke: 데이터 추가 및 갱신을 위한 트랜잭션. invoke 트랜잭션은 새 블록을 생성한다. 따라서 트랜잭션 흐름은 다음과 같다. 
    client(sdk) -> peer(readset/writeset을 함께 전달) -> client(proposal 생성) -> orderer(proposal을 전달하여 readset/writeset을 검증 : 이중지불 문제 방지) -> client에서 블록 생성여부 확인 
    그후 orderer에서는 leader peer 에게 블록 생성 여부를 전파하고, 해당 블록을 leader peer 가 받아간 뒤에 자신을 따르는 follower 들에게 gossip으로 전파.
2. 하이퍼레저 패브릭에서 MVCC 충돌이란 무엇인가요
  * HLF는 블록 생성 시 데이터 검증을 readset 과 wirteset 을 비교하여 검증한다. 이때 peer 에서 생성된 readset/writeset 과 orderer 에서 검증한 readset/writeset 이 다를 경우, MVCC 충돌을 발생한다. 즉, 한 블록타임에 동일 원장데이터를 서로 다른 트랜잭션이 변경 시도시 발생하는 충돌이다. (이중지불문제)
3. 하이퍼레저 패브릭에서 MSP 란 무엇인가요
  * MSP(Membership Service Provider)로서, HLF 네트워크 상에서 트랜잭션을 만들기 위해 사용하는 인증서의 단위이다. 꼭 필요한 MSP는 CA certificate, Singer certificate, signer's private key 이며, 트랜잭션의 종류와 통신방식에 따라 필요한 파일이 추가된다. 
4. 하이퍼레저 패브릭에서 Fabric-CA가 하는 역할은 무엇인가요
  * HLF-CA 는 HLF에서 트랜잭션을 만들기 위한 사용자를 등록하고, 해당 사용자가 원할 때 사용자의 identity 에 맞는 MSP를 제공하며(enroll), 필요에 따라 해당 identity 를 삭제 혹은 만료시킨다. 
5. 하이퍼레저 패브릭에서 RWSet이란 무엇인가요 
  * 쉽게 말하면, 이중지불문제를 방지하고 속도를 높이기 위한 transaction 시뮬레이션 검증 세트이다. 어떤 트랜잭션이 원장데이터를 바꾸기 위해 읽은 데이터(readset)과 원장 데이터 변경 후의 데이터(writeset)을 시뮬레이션 한 후, 블록에 쓰여지기전 이 데이터를 커미터 피어와 오더러 가 검증하여, 이 검증을 통과한 트랜잭션 데이터만 블록에 추가한다. 
6. 하이퍼레저 패브릭에서 블룸 필터는 어떻게 사용 되나요
7. 하이퍼레저 패브릭에서 ACL 은 어떤 정보를 어떻게 가져와서 적용 되나요
  * ACL은 Channel 의 설정 (config block) 을 변경하기 위한 트랜잭션을 어떤 MSP가 수행하게 할지 제어하는 설정이다. HLF 네트워크 설정 시 ACL을 설정할 수 있으며, 참여하는 모든 organization 의 admin / user 레벨의 msp 로 설정할 수도 있고, 특정 orgazization의 유저만 설정이 가능하도록 제어도 가능하다.
8. 하이퍼레저 패브릭에서 저장용량을 줄이기 위한 prunning은 어떻게 할 수 있을까요
  * HLF에서 prunning 기능은 아직(1.4.3) 에서 간단한 소개만 나와있다. HLF에서 MVCC / VSCC / CSCC 와 같은 원장 데이터 변경 실패 블록에 대한 데이터 역시 블록데이터로써 블록에 추가된다. prunning은 이런 트랜잭션 실패 데이터들을 블록에서 걷어내내는 대신 hash chain만 남기는 작업을 할 것이다. 
9. 하이퍼레저 패브릭에서 Kafka 는 왜 사용 되나요? RAFT 는 왜 등장 한 걸 까요?
  * Kafka는 Zap 알고리즘을 사용하는 대표적인 분산네트워크 컨센서스 알고리즘을 갖고 있다. HLF에서 Orderer 는 트랜잭션의 순서를 정하고 트랜잭션간의 순서를 맞추어 블록을 생성한다. 따라서 프로덕션 레벨의 HFL는 여러 대 의 orderer 들을 컨센서스로 묶는 알고리즘이 필요하다. 따라서 HLF Kafka Orderer 모델은 Zap 알고리즘을 사용하여 여러 Orderer에서 처리 되는 트랜잭션을 검증하게 된다.
  * RAFT 는 노드 들 중 리더 노드만이 메시지를 다른 노드에서 전파할 수 있는 특징이 있다. RAFT orderer 는 누가 RAFT 클러스터 내부에서 리더인지 알고 있으며, 따라서 모든 트랜잭션은 리더로 들어오게 된다. 이 트랜잭션은 RAFT의 LOG 로 처리가 되며, 리더는 이 LOG를 처리하여 각 팔로워에서 전달하게 된다. 각 팔로워는 전달받은(append 된) 트랜잭션으로 블록을 생성하게 되며, 이를 통해 모든 RAFT orderer 가 동일한 순서의 블록을 갖을 수 있게 된다. 
10. 하이퍼레저 패브릭에서 토큰은 만들 수 있나요?  FabToken 왜 만들어 졌을까요?  
11. 하이퍼레저 패브릭에서 리더피어와 앵커피어란 무엇인가요?
  * leader : 해당 organization 안에서 오더러에게 데이터를 받아오고 전파하기 위한 역할을 하는 피어
  * anchor : cross organization 트랜잭션 시 각 organiation 의 endpoint 역할
12. 하이퍼레저 패브릭에서 Gossip Protocol 는 왜 사용하나요?  
  * 피어 간 상태 변화 통신 및 데이터 검증을 위해 사용된다. 특히, channel의 멤버쉽관리와 anchor 피어와 리더피어 선출과 관련된 피어간 상태 를 gossip을 통해 연결된 모든 피어가 공유하며, private block data 전파 역시 gossip을 통해 이루어진다. 

### 암호학
1. HMAC / PKI / ECDSA는 무엇인가요
2. diffie-hellman 키 교환 알고리즘은 무엇인가요? 이더리움에서는 왜 사용하나요 
3. 하이퍼레저 패브릭의 ECcert 란 무엇인가요? 패브릭에서는 왜 사용하나요 
4. 하이퍼레저 패브릭의 TCert 는 왜 없어졌고, 대체제는 무엇인가요 
5. Schnorr signature는 무엇인가요?
6. 이더리움에서 영지식증명으로 활용 할 수 있는 것은 무엇이 있을까요
7. 하이퍼레저 패브릭에서 영지식증명으로 활용 할 수 있는 것은 무엇이 있을까요
8. ECC 개인키,공개키는 수학적으로 어떻게 만들어지며 비트코인의 secp256k1 소스를 보고 함수를 설명 해 주세요.

### 컨센서스
1. CFT와 BFT의 차이는 무엇인가요 
  * CFT(Crash Fault Tolerance): 네트워크를 구성하고 있는 노드들 중 한 노드가 깨지더라도 네트워크를 유지하는 합의이다. 
  * BFT(Byzantine Fault Tolerance): 네트워크를 구성하고 있는 노드들 중 악의를 갖는 노드를 허용하지 않는 합의이다. 단순히 노드 실패 허용 합의 알고리즘보다 복잡하다. 왜냐하면 악의를 갖지 않는 노드를 확인하는 연산역시 수행해야하기 때문이다. HLF과 같은 프라이빗 블록체인에서는 신원이 보증된 구성원들만 네트워크에 참여하기 때문에, CFT를 적용한다. 
2. RAFT 에서 리더 선출은 어떻게 하나요? 
3. PBFT 알고리즘은 무엇인가요
4. DPOS 알고리즘은 무엇인가요

기타

1. 하이퍼레져 패브릭 Indy 란
2. EOS에서 트랜잭션 수수료는?



### 블록체인 소프트웨어 일반/C++/Java/Go 
#### 소프트웨어 일반/설계
1. inheritance보다 Composition을 사용하라는 말은 무슨 의미인가요?
2. 주로 사용하는 리팩토링 3가지를 말해 주세요.
3. 디자인패턴은 표현(구조)보다는 의도가 중요하다는 말은 무슨 의미인가요?
4. 예외에 대해서 어떻게 생각하시나요? (예외 처리에 대한 6가지 화두 참고)
5. 동기,비동기,블록,논블록은 무엇이라고 생각하나요?
6. 잠금 없는 동시성 프로그래밍이란 무엇인가요?
7. Actor 패턴과 Go언어의 CSP 모델의 차이점은 무엇인가요?
8. 공간(메모리)를 낭비해서 성능을 높이는 방식의 예를 3가지만 들어주세요.

#### 자바
1. 자바의 메서드 인자 전달 방식과 Shallow Copy / Deep Copy 에 대해 설명 해주세요.
2. 자바의 HashMap 은 어떻게 동작하나요?
3. 자바 리플렉션은 무엇이며, 활용처가 어떤게 있을 까요?

#### C++
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
#### Golang
1. Go의 덕타이핑의 장,단점은 무엇인가요?
2. Go에서 고루틴&채널은 무엇인가요? 
3. Go에서 select 문은 어떻게 사용되나요? 아래 코드를 설명 해 주세요.
```go
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
```
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
