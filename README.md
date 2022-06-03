

## 0. 프로세스 상세 정보 용어
  
	PID : 프로세서 아이디
  
	USER : 사용자 (실행시킨 계정)
  
	PR : priority의 약어로 실행할 때의 우선순위
  
	NI : nice의 약어로 일의 nice value 값 ( 마이너스가 우선순위 높음)
  
	VIRT :프로세스에 할당된 가상 메모리의 전체 용량 (SWAP + RES)
  
	RES : 현재 프로세스가 사용하는 물리적인 메모리 양
  
	SHR : shared memory의 약어로 다른 프로세스와 공유하고 있는 메모리의 양
  
	S : 프로세스의 상태 (R - 작업중, D - I/O 대기, S - sleeping, Z - 부모 프로세스가 죽은 자식 프로세스 등)
  
	%CPU : 프로세서가 사용한 CPU 시간의 백분율 (사용률)
  
	%MEM : 프로세서가 사용하는 메모리의 사용률
  
	TIME+ : 현재까지 사용된 CPU 시간
  
	COMMAND : 실행된 명령어 
  
	Tasks : 프로세스의 개수
  


## 1. 리눅스 명령어 ( like 윈도우 작업관리자 )


	# top : 시스템 자원 사용 현황 출력하는 함수
  
		[ 출력 라인 별 해석 ]
    
		1라인 : 시스템 부팅 이후 총 사용시간(00시간 전에 서버가 구동), 사용자 수(users), 평균 부하 정보 - 얼마나 일하는지(load average)
      
		2라인 : 실행 중인 총 task 수(total)와 실행(running), 대기(sleeping), 중단(stopped), 좀비(zombie) 상태의 프로세스 수
      
		3라인 : CPU 사용률 정보 (%CPU(s))
    
		4라인 : 메모리 총량(total)과 사용현황 (used, free, buffers)
    
		5라인 : swap 공간(total)과 현황 (used, free, cached Mem)
    
		6라인 ~ : 실행 중인 프로세스들 상세 정보( 정렬 순서 : CPU 사용량 내림차순 )
    
		+ 실행 중인 명령어를 종료하려면 q
		
		
<img width="1000" src="https://user-images.githubusercontent.com/66362449/171820165-2ee90738-7956-417c-84bb-c6abe5d86d74.png">

		

	# ps : 실시간으로 변경되는 프로세스의 상태 정보 (명령어 실행 시점의 정보)
  
		[ 옵션 ]
    
		옵션 없음 : 현재 명령을 실행한 터미널 상의 사용자 프로세스 실행 정보
    
		x : 터미널에 관계없이 실행 중인 프로세스 정보를 출력하는 옵션
    
		u : 프로세스를 실행한 사용자의 정보를 출력하는 옵션
    
		a : 다른 사용자의 프로세스 실행 상태 정보도 출력하는 옵션
    
		-A : 모든 프로세스 출력하는 옵션
    
		-l : 자세한 정보
 <img width="319" alt="ps" src="https://user-images.githubusercontent.com/66362449/171822320-1f09f113-6b07-40d7-9062-33618693510e.png">



	# jobs : 백드라운드로 실행되는 작업의 상태를 표시하는 명령어
  
		명령어 사용 : jobs [옵션] [작업번호] (작업번호 - 별도로 부여)
    
		[ 작업의 상태 값 ]
    
		Running : 작업 진행 중
    
		Done : 작업이 완료 -> 0반환
    
		Done(code) : 작업이 완료 -> 0이 아닌 code 반환
    
		Stopped : 작업 일시 중단
    
		Stopped(SIGTSTP) : SIGTSTP 시그널이 작업을 일시 중단
    
		Stopped(SIGSTOP) : SIGSTOP 시그널이 작업을 일시 중단
    
		Stopped(SIGTTIN) : SIGTTIN 시그널이 작업을 일시 중단
    
		Stopped(SIGTTOU) : SIGTTOU 시그널이 작업을 일시 중단
    
		[ 옵션 ]
    
		-l : 프로세스 그룹 ID 출력
    
		-n : 프로세스 그룹 중 대표 프로세스 ID 출력
    
		-p : 각 프로세스 ID에 대해 한 행씩 출력
    

	# kill : 실행 중인 프로세스를 종료하는 명령어 (Ctrl + C와 같은 기능)
  
		명령어 사용 : kill [옵션] 종료할 PID 
    
		[ 옵션 ]
    
		옵션 x : wkrdjqwhdfy
    
		-9 : 강제종료
    
		-15 : 작업종료
    
		(%작업번호) : 해당 작업 종료
    


## 2. vim editor 매크로 사용법

    1) q + (알파벳) : 특정 알파벳에 매크로를 저장 
    
    2) 매크로로 저장하고 싶은 동작
    
    3) q : recoding 종료
    
    4) @(알파벳) : 매크로 실행 (@@ : 방금 실행한 매크로 실행, n@(알파벳) : 매크로 n회 실행)
    
    " 추가 핵심 키 "
    ctrl + a : 숫자 증가 
    ctrl + x : 숫자 감소
  
     
----
> 컴퓨터공학과 학생답게 인사는 코드로 해보겠습니다!

`printf("bye~ everyone!");`
