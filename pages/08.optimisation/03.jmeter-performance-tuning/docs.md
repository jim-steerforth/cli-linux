---
title: ' JMeter Performance Tuning'
media_order: 'Jmeter1.png,jmeter2.png,Jmeter3.png'
taxonomy:
    category:
        - docs
---

<p>  Apache JMeter can be used to check speed on a Moodle install and see what performance gains can be made with different configurations. Do this only  when setting up as the load will kill performance on an Production Server. Also be careful on shared hosting as limits will soon be reached.</p>

<p>  First step on a clean Moodle Install is to create a test course.</p>

   
<tt>  Dashboard -> Site administration ->  Development  -> Make test course</tt>
  
  <p>Start with XS or S, if the Jmeter tests run qickly then you can always step up.</p>

 
<tt>  Dashboard -> Site administration ->  Development  ->  Make JMeter test plan</tt> 
<p>  First you need to set a password for the course users in the config.php file in your Moodle code folder (e.g. $CFG->tool_generator_users_password = 'moodle';) </p>


 <p>Base the test plan on your new test course.</p>

 
 <p>You should get two files to download, mine were called testplan_202009150449_6377.jmx and users_202009150449_9289.csv. Copy both to a machine runinng a GUI because jMeter will be run in GUI mode.</p>
 
<p>To install Jmeter go to <a href="http://jmeter.apache.org/download_jmeter.cgi">this downlaod page</a>. On my Linux machine I also had to install beanshell with:</p>

<tt>sudo apt-get install bsh</tt>
<p>Open JMeter and open your jmx file.</p>
![](Jmeter1.png)

<p>With the test plan loaded, go to the warmup site and Default Site Request set the protocol<p>Open JMeter and open your jmx file.</p>on the web server to http and the server name or IP to the websire address. Under CSV users data, set the filename to your CSV file.  </p>
![](jmeter2.png)
<p>Right click the Test Plan at the top of the tree, select Add  and then Listener. Choose the top three  of View Results Tree, Summary Report and Aggregate Report.</p>![](Jmeter3.png)

<p> This is the results ofa  test run on a small Moodle test course on the Hostvds,com loq end server as describe dxin server benchmarks. There wasw no config changes and no optimisation at this point, Run took 19:04.
    
   </p>
    
    

<table cellspacing="0" cellpadding="4" border="1" width="95%">
  <tr>
    <!-- Row 1 Column 1 -->
    <td>
      <b>
        Label
      </b>
    </td>
    <!-- Row 1 Column 2 -->
    <td>
      <b>
        # Samples
      </b>
    </td>
    <!-- Row 1 Column 3 -->
    <td>
      <b>
        Average
      </b>
    </td>
    <!-- Row 1 Column 4 -->
    <td>
      <b>
        Median
      </b>
    </td>
    <!-- Row 1 Column 5 -->
    <td>
      <b>
        90% Line
      </b>
    </td>
    <!-- Row 1 Column 6 -->
    <td>
      <b>
        95% Line
      </b>
    </td>
    <!-- Row 1 Column 7 -->
    <td>
      <b>
        99% Line
      </b>
    </td>
    <!-- Row 1 Column 8 -->
    <td>
      <b>
        Min
      </b>
    </td>
    <!-- Row 1 Column 9 -->
    <td>
      <b>
        Max
      </b>
    </td>
    <!-- Row 1 Column 10 -->
    <td>
      <b>
        Error %
      </b>
    </td>
    <!-- Row 1 Column 11 -->
    <td>
      <b>
        Throughput
      </b>
    </td>
    <!-- Row 1 Column 12 -->
    <td>
      <b>
        Received KB/sec
      </b>
    </td>
    <!-- Row 1 Column 13 -->
    <td>
      <b>
        Sent KB/sec
      </b>
    </td>
  </tr>
  <tr>
    <!-- Row 2 Column 1 -->
    <td>
      <b>
        Frontpage not logged
      </b>
    </td>
    <!-- Row 2 Column 2 -->
    <td>
      180
    </td>
    <!-- Row 2 Column 3 -->
    <td>
      2442
    </td>
    <!-- Row 2 Column 4 -->
    <td>
      1446
    </td>
    <!-- Row 2 Column 5 -->
    <td>
      5510
    </td>
    <!-- Row 2 Column 6 -->
    <td>
      8827
    </td>
    <!-- Row 2 Column 7 -->
    <td>
      9570
    </td>
    <!-- Row 2 Column 8 -->
    <td>
      1377
    </td>
    <!-- Row 2 Column 9 -->
    <td>
      10024
    </td>
    <!-- Row 2 Column 10 -->
    <td>
      0.000%
    </td>
    <!-- Row 2 Column 11 -->
    <td>
      0.18797
    </td>
    <!-- Row 2 Column 12 -->
    <td>
      5.61
    </td>
    <!-- Row 2 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 3 Column 1 -->
    <td>
      <b>
        View login page
      </b>
    </td>
    <!-- Row 3 Column 2 -->
    <td>
      180
    </td>
    <!-- Row 3 Column 3 -->
    <td>
      1123
    </td>
    <!-- Row 3 Column 4 -->
    <td>
      1081
    </td>
    <!-- Row 3 Column 5 -->
    <td>
      1208
    </td>
    <!-- Row 3 Column 6 -->
    <td>
      1258
    </td>
    <!-- Row 3 Column 7 -->
    <td>
      2498
    </td>
    <!-- Row 3 Column 8 -->
    <td>
      166
    </td>
    <!-- Row 3 Column 9 -->
    <td>
      3400
    </td>
    <!-- Row 3 Column 10 -->
    <td>
      1.111%
    </td>
    <!-- Row 3 Column 11 -->
    <td>
      0.18691
    </td>
    <!-- Row 3 Column 12 -->
    <td>
      4.45
    </td>
    <!-- Row 3 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 4 Column 1 -->
    <td>
      <b>
        Login
      </b>
    </td>
    <!-- Row 4 Column 2 -->
    <td>
      180
    </td>
    <!-- Row 4 Column 3 -->
    <td>
      5118
    </td>
    <!-- Row 4 Column 4 -->
    <td>
      4193
    </td>
    <!-- Row 4 Column 5 -->
    <td>
      8531
    </td>
    <!-- Row 4 Column 6 -->
    <td>
      10000
    </td>
    <!-- Row 4 Column 7 -->
    <td>
      12703
    </td>
    <!-- Row 4 Column 8 -->
    <td>
      1388
    </td>
    <!-- Row 4 Column 9 -->
    <td>
      12806
    </td>
    <!-- Row 4 Column 10 -->
    <td>
      1.111%
    </td>
    <!-- Row 4 Column 11 -->
    <td>
      0.18596
    </td>
    <!-- Row 4 Column 12 -->
    <td>
      39.29
    </td>
    <!-- Row 4 Column 13 -->
    <td>
      0.15
    </td>
  </tr>
  <tr>
    <!-- Row 5 Column 1 -->
    <td>
      <b>
        Frontpage logged
      </b>
    </td>
    <!-- Row 5 Column 2 -->
    <td>
      180
    </td>
    <!-- Row 5 Column 3 -->
    <td>
      3698
    </td>
    <!-- Row 5 Column 4 -->
    <td>
      3360
    </td>
    <!-- Row 5 Column 5 -->
    <td>
      6045
    </td>
    <!-- Row 5 Column 6 -->
    <td>
      7055
    </td>
    <!-- Row 5 Column 7 -->
    <td>
      7665
    </td>
    <!-- Row 5 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 5 Column 9 -->
    <td>
      8192
    </td>
    <!-- Row 5 Column 10 -->
    <td>
      7.222%
    </td>
    <!-- Row 5 Column 11 -->
    <td>
      0.18672
    </td>
    <!-- Row 5 Column 12 -->
    <td>
      36.54
    </td>
    <!-- Row 5 Column 13 -->
    <td>
      0.1
    </td>
  </tr>
  <tr>
    <!-- Row 6 Column 1 -->
    <td>
      <b>
        View course
      </b>
    </td>
    <!-- Row 6 Column 2 -->
    <td>
      180
    </td>
    <!-- Row 6 Column 3 -->
    <td>
      2211
    </td>
    <!-- Row 6 Column 4 -->
    <td>
      2170
    </td>
    <!-- Row 6 Column 5 -->
    <td>
      2594
    </td>
    <!-- Row 6 Column 6 -->
    <td>
      3299
    </td>
    <!-- Row 6 Column 7 -->
    <td>
      3979
    </td>
    <!-- Row 6 Column 8 -->
    <td>
      1
    </td>
    <!-- Row 6 Column 9 -->
    <td>
      4757
    </td>
    <!-- Row 6 Column 10 -->
    <td>
      1.111%
    </td>
    <!-- Row 6 Column 11 -->
    <td>
      0.18506
    </td>
    <!-- Row 6 Column 12 -->
    <td>
      29.75
    </td>
    <!-- Row 6 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 7 Column 1 -->
    <td>
      <b>
        Logout
      </b>
    </td>
    <!-- Row 7 Column 2 -->
    <td>
      180
    </td>
    <!-- Row 7 Column 3 -->
    <td>
      1646
    </td>
    <!-- Row 7 Column 4 -->
    <td>
      1487
    </td>
    <!-- Row 7 Column 5 -->
    <td>
      1839
    </td>
    <!-- Row 7 Column 6 -->
    <td>
      2721
    </td>
    <!-- Row 7 Column 7 -->
    <td>
      4366
    </td>
    <!-- Row 7 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 7 Column 9 -->
    <td>
      11446
    </td>
    <!-- Row 7 Column 10 -->
    <td>
      2.222%
    </td>
    <!-- Row 7 Column 11 -->
    <td>
      0.16566
    </td>
    <!-- Row 7 Column 12 -->
    <td>
      5.67
    </td>
    <!-- Row 7 Column 13 -->
    <td>
      0.07
    </td>
  </tr>
  <tr>
    <!-- Row 8 Column 1 -->
    <td>
      <b>
        View a page activity
      </b>
    </td>
    <!-- Row 8 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 8 Column 3 -->
    <td>
      2200
    </td>
    <!-- Row 8 Column 4 -->
    <td>
      1882
    </td>
    <!-- Row 8 Column 5 -->
    <td>
      2539
    </td>
    <!-- Row 8 Column 6 -->
    <td>
      4640
    </td>
    <!-- Row 8 Column 7 -->
    <td>
      7043
    </td>
    <!-- Row 8 Column 8 -->
    <td>
      1412
    </td>
    <!-- Row 8 Column 9 -->
    <td>
      7349
    </td>
    <!-- Row 8 Column 10 -->
    <td>
      0.000%
    </td>
    <!-- Row 8 Column 11 -->
    <td>
      0.16919
    </td>
    <!-- Row 8 Column 12 -->
    <td>
      22.91
    </td>
    <!-- Row 8 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 9 Column 1 -->
    <td>
      <b>
        View course again
      </b>
    </td>
    <!-- Row 9 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 9 Column 3 -->
    <td>
      2724
    </td>
    <!-- Row 9 Column 4 -->
    <td>
      2171
    </td>
    <!-- Row 9 Column 5 -->
    <td>
      5571
    </td>
    <!-- Row 9 Column 6 -->
    <td>
      7134
    </td>
    <!-- Row 9 Column 7 -->
    <td>
      7833
    </td>
    <!-- Row 9 Column 8 -->
    <td>
      1
    </td>
    <!-- Row 9 Column 9 -->
    <td>
      10690
    </td>
    <!-- Row 9 Column 10 -->
    <td>
      1.333%
    </td>
    <!-- Row 9 Column 11 -->
    <td>
      0.16902
    </td>
    <!-- Row 9 Column 12 -->
    <td>
      27.21
    </td>
    <!-- Row 9 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 10 Column 1 -->
    <td>
      <b>
        View a forum activity
      </b>
    </td>
    <!-- Row 10 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 10 Column 3 -->
    <td>
      4866
    </td>
    <!-- Row 10 Column 4 -->
    <td>
      3439
    </td>
    <!-- Row 10 Column 5 -->
    <td>
      8868
    </td>
    <!-- Row 10 Column 6 -->
    <td>
      14534
    </td>
    <!-- Row 10 Column 7 -->
    <td>
      22107
    </td>
    <!-- Row 10 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 10 Column 9 -->
    <td>
      22359
    </td>
    <!-- Row 10 Column 10 -->
    <td>
      4.000%
    </td>
    <!-- Row 10 Column 11 -->
    <td>
      0.16734
    </td>
    <!-- Row 10 Column 12 -->
    <td>
      56.83
    </td>
    <!-- Row 10 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 11 Column 1 -->
    <td>
      <b>
        View a forum discussion
      </b>
    </td>
    <!-- Row 11 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 11 Column 3 -->
    <td>
      6413
    </td>
    <!-- Row 11 Column 4 -->
    <td>
      3978
    </td>
    <!-- Row 11 Column 5 -->
    <td>
      12106
    </td>
    <!-- Row 11 Column 6 -->
    <td>
      28682
    </td>
    <!-- Row 11 Column 7 -->
    <td>
      48054
    </td>
    <!-- Row 11 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 11 Column 9 -->
    <td>
      49368
    </td>
    <!-- Row 11 Column 10 -->
    <td>
      9.333%
    </td>
    <!-- Row 11 Column 11 -->
    <td>
      0.16335
    </td>
    <!-- Row 11 Column 12 -->
    <td>
      79.1
    </td>
    <!-- Row 11 Column 13 -->
    <td>
      0.03
    </td>
  </tr>
  <tr>
    <!-- Row 12 Column 1 -->
    <td>
      <b>
        Fill a form to reply a forum discussion
      </b>
    </td>
    <!-- Row 12 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 12 Column 3 -->
    <td>
      4625
    </td>
    <!-- Row 12 Column 4 -->
    <td>
      2872
    </td>
    <!-- Row 12 Column 5 -->
    <td>
      11136
    </td>
    <!-- Row 12 Column 6 -->
    <td>
      15515
    </td>
    <!-- Row 12 Column 7 -->
    <td>
      27341
    </td>
    <!-- Row 12 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 12 Column 9 -->
    <td>
      27550
    </td>
    <!-- Row 12 Column 10 -->
    <td>
      5.333%
    </td>
    <!-- Row 12 Column 11 -->
    <td>
      0.16513
    </td>
    <!-- Row 12 Column 12 -->
    <td>
      45.88
    </td>
    <!-- Row 12 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 13 Column 1 -->
    <td>
      <b>
        Send the forum discussion reply
      </b>
    </td>
    <!-- Row 13 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 13 Column 3 -->
    <td>
      1329
    </td>
    <!-- Row 13 Column 4 -->
    <td>
      815
    </td>
    <!-- Row 13 Column 5 -->
    <td>
      1287
    </td>
    <!-- Row 13 Column 6 -->
    <td>
      3341
    </td>
    <!-- Row 13 Column 7 -->
    <td>
      13666
    </td>
    <!-- Row 13 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 13 Column 9 -->
    <td>
      17816
    </td>
    <!-- Row 13 Column 10 -->
    <td>
      15.333%
    </td>
    <!-- Row 13 Column 11 -->
    <td>
      0.16589
    </td>
    <!-- Row 13 Column 12 -->
    <td>
      1.52
    </td>
    <!-- Row 13 Column 13 -->
    <td>
      0.1
    </td>
  </tr>
  <tr>
    <!-- Row 14 Column 1 -->
    <td>
      <b>
        View course once more
      </b>
    </td>
    <!-- Row 14 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 14 Column 3 -->
    <td>
      2948
    </td>
    <!-- Row 14 Column 4 -->
    <td>
      2136
    </td>
    <!-- Row 14 Column 5 -->
    <td>
      4554
    </td>
    <!-- Row 14 Column 6 -->
    <td>
      6885
    </td>
    <!-- Row 14 Column 7 -->
    <td>
      16208
    </td>
    <!-- Row 14 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 14 Column 9 -->
    <td>
      21154
    </td>
    <!-- Row 14 Column 10 -->
    <td>
      2.667%
    </td>
    <!-- Row 14 Column 11 -->
    <td>
      0.16666
    </td>
    <!-- Row 14 Column 12 -->
    <td>
      26.51
    </td>
    <!-- Row 14 Column 13 -->
    <td>
      0.04
    </td>
  </tr>
  <tr>
    <!-- Row 15 Column 1 -->
    <td>
      <b>
        View course participants
      </b>
    </td>
    <!-- Row 15 Column 2 -->
    <td>
      150
    </td>
    <!-- Row 15 Column 3 -->
    <td>
      2307
    </td>
    <!-- Row 15 Column 4 -->
    <td>
      2155
    </td>
    <!-- Row 15 Column 5 -->
    <td>
      3663
    </td>
    <!-- Row 15 Column 6 -->
    <td>
      4499
    </td>
    <!-- Row 15 Column 7 -->
    <td>
      7183
    </td>
    <!-- Row 15 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 15 Column 9 -->
    <td>
      7243
    </td>
    <!-- Row 15 Column 10 -->
    <td>
      5.333%
    </td>
    <!-- Row 15 Column 11 -->
    <td>
      0.1686
    </td>
    <!-- Row 15 Column 12 -->
    <td>
      25.94
    </td>
    <!-- Row 15 Column 13 -->
    <td>
      0.03
    </td>
  </tr>
  <tr>
    <!-- Row 16 Column 1 -->
    <td>
      <b>
        TOTAL
      </b>
    </td>
    <!-- Row 16 Column 2 -->
    <td>
      2280
    </td>
    <!-- Row 16 Column 3 -->
    <td>
      3085
    </td>
    <!-- Row 16 Column 4 -->
    <td>
      2172
    </td>
    <!-- Row 16 Column 5 -->
    <td>
      5350
    </td>
    <!-- Row 16 Column 6 -->
    <td>
      7665
    </td>
    <!-- Row 16 Column 7 -->
    <td>
      17816
    </td>
    <!-- Row 16 Column 8 -->
    <td>
      0
    </td>
    <!-- Row 16 Column 9 -->
    <td>
      49368
    </td>
    <!-- Row 16 Column 10 -->
    <td>
      3.860%
    </td>
    <!-- Row 16 Column 11 -->
    <td>
      1.99279
    </td>
    <!-- Row 16 Column 12 -->
    <td>
      328.67
    </td>
    <!-- Row 16 Column 13 -->
    <td>
      0.66
    </td>
  </tr>
</table>








 
 
