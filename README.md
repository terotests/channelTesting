
# channelTesting

The library includes some template filesystems useful for testing the system.

```javascript


```
















   

 


   
#### Class channelTesting


- [pwFilesystem](README.md#channelTesting_pwFilesystem)
- [testFilesystem1](README.md#channelTesting_testFilesystem1)



   
    
    


   
      
            
#### Class testFs





   


   



      
    





   
# Class channelTesting


The class has following internal singleton variables:
        
        
### channelTesting::constructor( t )

```javascript

```
        
### <a name="channelTesting_pwFilesystem"></a>channelTesting::pwFilesystem(t)

The test users are &quot;Tero&quot; with password &quot;teropw&quot; and &quot;Juha&quot; with password &quot;juhapw&quot;. Juha has groups &quot;users&quot; and Tero has groups &quot;users&quot; and &quot;admins&quot;
```javascript

// The password and user infra, in the simulation environment:

var pwData = {
                "groups":{},
                "domains":{},
                "users":{
                        "505d18cbea690d03eb240729299468071c9f133758b6c527e2dddd458de2ad36":"ee8f858602fabad8e7f30372a4d910ab875b869d52d9206c0257d59678ba6031:id1:",
                        "dce8981dec48df66ed7b139dfd1a680aa1d404a006264f24fda9e0e598c1ac8a":"add2bbda7947ab86c2e9f277ccee254611bedd1e3b8542113ea36931c1fdbf3e:id2:"},
                "udata":{"id1":"{\"userName\":\"Tero\",\"domain\":\"\",\"hash\":\"505d18cbea690d03eb240729299468071c9f133758b6c527e2dddd458de2ad36\",\"groups\":\[\"users\",\"admins\"\]}",
                         "id2":"{\"userName\":\"Juha\",\"domain\":\"\",\"hash\":\"dce8981dec48df66ed7b139dfd1a680aa1d404a006264f24fda9e0e598c1ac8a\",\"groups\":\[\"users\"\]}"}};

var pwFiles = fsServerMemory("pwServer1", pwData);

return pwFiles;
```

### <a name="channelTesting_testFilesystem1"></a>channelTesting::testFilesystem1(t)

Test filesystem 1 represents a channel &quot;my/channel&quot; with one fork with channelID &quot;my/channel/myFork&quot;.
```javascript
var fsData = {
    "my" : {
        "channel" : {
            "journal.1" : "",
            "file.2" :  JSON.stringify({
                data : { 
                    path : "M22.441,28.181c-0.419,0-0.835-0.132-1.189-0.392l-5.751-4.247L9.75,27.789c-0.354,0.26-0.771,0.392-1.189,0.392c-0.412,0-0.824-0.128-1.175-0.384c-0.707-0.511-1-1.422-0.723-2.25l2.26-6.783l-5.815-4.158c-0.71-0.509-1.009-1.416-0.74-2.246c0.268-0.826,1.037-1.382,1.904-1.382c0.004,0,0.01,0,0.014,0l7.15,0.056l2.157-6.816c0.262-0.831,1.035-1.397,1.906-1.397s1.645,0.566,1.906,1.397l2.155,6.816l7.15-0.056c0.004,0,0.01,0,0.015,0c0.867,0,1.636,0.556,1.903,1.382c0.271,0.831-0.028,1.737-0.739,2.246l-5.815,4.158l2.263,6.783c0.276,0.826-0.017,1.737-0.721,2.25C23.268,28.053,22.854,28.181,22.441,28.181L22.441,28.181z", 
                    fill : "red"            
                },
                __id : "id1",
                __acl : "A:g:users@:rwx\nA:g:admins@:rwxadtTnNcCy"
            }),
            "journal.2" : JSON.stringify([4, "fill", "yellow", "red", "id1"])+"\n",
            "ch.settings" : JSON.stringify({
                version : 2,                        // version of the channel
                channelId : "my/channel",           // ID of this channel
                journalLine : 1,
                utc : 14839287897                   // UTC timestamp of creation                
            }),
            "forks"  : JSON.stringify({                 // == forks on list of forks
                    fromJournalLine : 1,               
                    version : 1,                        
                    channelId : "my/channel/myFork",    
                    fromVersion : 2,                    
                    from : "my/channel",                
                    to :  "my/channel/myFork",         
                    name : "test of fork",
                    utc : 14839287897                  
                }),
            "myFork" : {
                "journal.1" : JSON.stringify([4, "fill", "blue", "yellow", "id1"])+"\n",
                "ch.settings" : JSON.stringify({
                    fromJournalLine : 1,                // from which line the fork starts
                    version : 1,                        // version of the channel
                    channelId : "my/channel/myFork",    // ID of this channel
                    fromVersion : 2,                    // version of the fork's source
                    from : "my/channel",                // the fork channels ID
                    to :  "my/channel/myFork",          // forks target channel
                    name : "test of fork",
                    utc : 14839287897                   // UTC timestamp of creation
                })
            }
        }
    }    
};

return 
```



   
    
    


   
      
            
# Class testFs


The class has following internal singleton variables:
        
* _instanceCache
        
        
### testFs::constructor( t )

```javascript

```
        


   


   



      
    




