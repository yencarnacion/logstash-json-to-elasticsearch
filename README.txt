Step 01:
  - Remove all newlines from json so as to leave one line
  - See http://stackoverflow.com/questions/1251999/how-can-i-replace-a-newline-n-using-sed
   $ cat input.json | sed -e ':a' -e 'N' -e '$!ba' -e 's/\n/ /g' > output01.json

Step 02:
  - Load single line json file into elasticsearch with logstash 
  - Remember to '$ unset JAVA_OPTS'
  - Remember to delete ~/.sincedb_* if not working
   $  ~/bin/logstash/bin/logstash  agent -f step02.conf 

