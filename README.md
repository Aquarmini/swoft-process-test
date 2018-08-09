<p align="center">
    <a href="https://github.com/swoft-cloud/swoft" target="_blank">
        <img src="http://qiniu.daydaygo.top/swoft-logo.png?imageView2/2/w/300" alt="swoft" />
    </a>
</p>

开启8个工作时的结果
~~~
$ ab -c 20 -n 100 http://127.0.0.1:8080/sleep
This is ApacheBench, Version 2.3 <$Revision: 1826891 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking 127.0.0.1 (be patient).....done


Server Software:        swoole-http-server
Server Hostname:        127.0.0.1
Server Port:            8080

Document Path:          /sleep
Document Length:        22 bytes

Concurrency Level:      20
Time taken for tests:   14.031 seconds
Complete requests:      100
Failed requests:        0
Total transferred:      44100 bytes
HTML transferred:       2200 bytes
Requests per second:    7.13 [#/sec] (mean)
Time per request:       2806.300 [ms] (mean)
Time per request:       140.315 [ms] (mean, across all concurrent requests)
Transfer rate:          3.07 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    1   0.4      0       2
Processing:  1003 2354 642.4   2004    3008
Waiting:     1002 2354 642.5   2004    3008
Total:       1004 2355 642.2   2005    3009
ERROR: The median and mean for the initial connection time are more than twice the standard
       deviation apart. These results are NOT reliable.

Percentage of the requests served within a certain time (ms)
  50%   2005
  66%   3005
  75%   3006
  80%   3006
  90%   3007
  95%   3007
  98%   3008
  99%   3009
 100%   3009 (longest request)
 ~~~
 
 开启16个工作的结果
 ~~~
 $ ab -c 20 -n 100 http://127.0.0.1:8080/sleep
 This is ApacheBench, Version 2.3 <$Revision: 1826891 $>
 Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
 Licensed to The Apache Software Foundation, http://www.apache.org/
 
 Benchmarking 127.0.0.1 (be patient).....done
 
 
 Server Software:        swoole-http-server
 Server Hostname:        127.0.0.1
 Server Port:            8080
 
 Document Path:          /sleep
 Document Length:        22 bytes
 
 Concurrency Level:      20
 Time taken for tests:   8.019 seconds
 Complete requests:      100
 Failed requests:        0
 Total transferred:      44100 bytes
 HTML transferred:       2200 bytes
 Requests per second:    12.47 [#/sec] (mean)
 Time per request:       1603.837 [ms] (mean)
 Time per request:       80.192 [ms] (mean, across all concurrent requests)
 Transfer rate:          5.37 [Kbytes/sec] received
 
 Connection Times (ms)
               min  mean[+/-sd] median   max
 Connect:        0    1   0.4      1       2
 Processing:  1001 1243 429.5   1003    2005
 Waiting:     1001 1243 429.6   1003    2005
 Total:       1002 1244 429.4   1004    2006
 
 Percentage of the requests served within a certain time (ms)
   50%   1004
   66%   1006
   75%   1007
   80%   2004
   90%   2004
   95%   2005
   98%   2005
   99%   2006
  100%   2006 (longest request)
 ~~~