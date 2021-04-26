linux에서 제공하는 operf 명령어와 분석하는 opreport를 통해 분석해보면


operf [run options] [other options]
run options에는 -s -p 
-s : system 전체에 대한 프로파일링
-p : 특정 process에 대한 프로파일링 

other options
--callgraph / -g : 특정 파일에서 어떤 function이 실행되었는지 추적
--separate-cpu / -c : 각각의 cpu들을 category화

opreport [options] [profile specification]
--debug-info / -g : 각각의 symbol에 대한 소스파일 보여줌.

--symbols / -l : symbol에 대해 표로 정리
--xml / -X : xml형식으로 output
              Show source file and line for each symbol.
--callgraph / -c : graph 정보를 보여줌.
