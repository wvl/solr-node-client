#Solr Client API

##Features
 - Support commands: Query, Delete, Update, Commit, Rollback, Optimize
 - Support Dismax Query Syntax
 - Support implicit conversion for `Date` Object to the supported format by Solr.
 More informations available about [the Solr Date Format](http://lucidworks.lucidimagination.com/display/LWEUG/Solr+Date+Format).

##History
 - _!WARNING!_ On the v0.0.3 I [standardized error handling](http://docs.nodejitsu.com/articles/errors/what-are-the-error-conventions) in asynchronous functions by returning them as the first argument to the current function's callback and not as the second argument like it's was the case on version < 0.0.3. This modification can break you code have a look to your code before you update.
 
##Install
    npm install solr-client
    
##Get started
    // Dependency
    var solr = require('solr-client');
    
    //Create Client
    var client = solr.createClient();
    
    //Add
    var doc = {
      field : 'value';
    }
    var callback = function(err,res){
      if(err) console.log(err);
      if(res) console.log(res);
    }
    client.add(doc,callback);
    client.commit(callback);


##Test
Before to run the test, start the Solr Server.
     
     vows --spec test/*
##Examples

Take a look in the [folder examples](https://github.com/lbdremy/solr-node-client/tree/master/examples).
