linux에서 제공하는 operf 명령어와 분석하는 opreport를 통해 분석해보면


operf [run options] [other options]

run options에는 -s -p 

-s : system 전체에 대한 프로파일링

-p : 특정 process에 대한 프로파일링 

other options

--callgraph / -g : 특정 파일에서 어떤 function이 실행되었는지 

--separate-cpu / -c : 각각의 cpu들을 category화

opreport [options] [profile specification]

--debug-info / -g : 각각의 symbol에 대한 소스파일 보여줌.

--symbols / -l : symbol에 대해 표로 정리

--xml / -X : xml형식으로 output

              Show source file and line for each symbol.
              
--callgraph / -c : graph 정보를 보여줌.

CPU별 sample과 symbol을 분석해보자.
![image](https://user-images.githubusercontent.com/61117544/116153707-b3129c00-a722-11eb-9aae-68dd3d81cf9c.png)

master core를 담당하고 있는 CPU 2번에서 pktgen실행 파일로부터 pktgen_script_save 함수를 CPU의 97.5346% 사용 중이다.

CPU 3번은 receive를 담당하고 있는 코어로 pktgen_script_save 함수를 CPU의 99.9997% 사용 중이다.

CPU 4번은 transmit를 담당하고 있는 코어로 pcap_filter가 84.9643%, pktgen_script_save가 7.2721%, pktgen_flags_string을 3.5186%, pktgen_port_stats를 2.4220% 사용중이다.
