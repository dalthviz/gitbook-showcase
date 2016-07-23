#Structure Data

The Structure Data...

```javascript
{
"artifacts" : { "UIDArtifact" :
                { "json" : http://localhost:63342/app/example.json",
                "name" : "Example Model", 
                "uuid" : "102" 
                },...
              },
"projects" : { "UIDProject" :
                { "administrators" : { "UIDUser" : true },                      
                "artifacts" : { "UIDArtifact" : true, }, 
                "configurators" : { "UIDUser" : true },             
                "description" : "Ejemplo", 
                "modelers" : { "UIDUsuario" : true},
                "name" : "Proyecto Ejemplo", 
                "parameters" : "http://localhost:8080/famosa.server", 
                "tags" : [ "Example" ] 
               },...
             },
"users" : { "UIDUser" : 
               { "name" : "Daniel Althviz", 
               "projects" : {"UIDProject" : true,...}, 
               "role" : true, 
               "uid" : "UIDUser",
               "user" : "d.althviz10@uniandes.edu.co" 
               },...
          }
}

```