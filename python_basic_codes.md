Python Basic Codes
==============================================================================
### run this before anything
```
import os
os.chdir("/Users/changli/Desktop/Course/Udacity/Machine_Learning/final_project") 
```

##Initiate Python Shell
```
python       #call from terminal
Working directory
pwd    #find current working directory
cd path      #change directory to path
```

##install or update modules
```
#in terminal
sudo pip install -U scikit-learn

#in IPython
!pip install -U scikit-learn

```
##See modules
'''
help('modules')
'''

##site packages
'''
import site
site.getsitepackages()
'''

##Error
###sciki-learn
Install new sciki-learn package without deleting old ones will create error message. 
```
ImportError: cannot import name inplace_column_scale
```
Solution: Manually delete all the sciki learn files under sit-package including sklearn folder, scikit_learn-0.16.1-py2.7.egg-info and then reinstall the package.



##Run Python file
```
python ‘name.py’ #run Python codes
```

##system path
The starting point must be an equivalent folder, such as "final_project"
One dot means staying with the current directory. Two dots means going one directory up.
```
import sys
sys.path.append("../tools/") 
```

##Run MongoDB in Terminal
```
sudo mongod
mongodb
show collections
```

###MapReduce Example
```
var mapFunction = function() {var key = this.userid; var value = {userid: this.userid, total_time: this.length,count: 1, avg_time: 0};emit( key, value );};

var reduceFunction = function(key, values) {var reducedObject = {userid: key, total_time: 0,count:0,avg_time:0}; values.forEach( function(value) {reducedObject.total_time += value.total_time; reducedObject.count += value.count;});return reducedObject;};

var finalizeFunction = function (key, reducedValue) {if (reducedValue.count > 0) reducedValue.avg_time = reducedValue.total_time / reducedValue.count; return reducedValue;};

db.sessions.mapReduce( mapFunction,reduceFunction, {out: "session_stat",finalize: finalizeFunction})
````
