#Structure Data

Based on documentation of [Firebase](https://firebase.google.com/docs/database/web/structure-data) for structuring data, the database must be built compactly (avoiding nesting). Thus, the information is structured in such a way that between entities, the relationships are handled with references between arrangements with pairs key-value, where the key is the identification of the element within the corresponding list (_artifacts_, _projects_, or _users_), while the value is set to true. Next, an example of this  structuring methodology is shown:

```javascript
1. {
2. "artifacts" : { "UIDArtifact" :
3.                { "json" : http://localhost:63342/app/example.json",
4.                "name" : "Example Model", 
5.                "uuid" : "102" 
6.                },...
7.              },
8. "projects" : { "UIDProject" :
9.               { "administrators" : { "UIDUser" : true },                      
10.             "artifacts" : { "UIDArtifact" : true, }, 
11.             "configurators" : { "UIDUser" : true },             
12.             "description" : "Ejemplo", 
13.             "modelers" : { "UIDUsuario" : true},
14.             "name" : "Proyecto Ejemplo", 
15.             "parameters" : "http://localhost:8080/famosa.server", 
16.             "tags" : [ "Example" ] 
17.              },...
18.             },
19. "users" : { "UIDUser" : 
20.              { "name" : "Daniel Althviz", 
21.            "projects" : {"UIDProject" : true,...}, 
22.            "role" : true, 
23.            "uid" : "UIDUser",
24.            "user" : "d.althviz10@uniandes.edu.co" 
25.             },...
26.           }
27. }
```
Thus, in the JSON, you can see the relationship between the artifact with identification **UIDArtifact** and the project with identification **UIDProject** (in the list of artifacts in the project the identification of the artifact with a value observed true is visible - line 10 -). In the same way, a similar relationship between the aforementioned project, and the user with identification "UIDUser", exists (in the user projects list -line 21- and  in the administrators, configurators and modelers lists of the project -lines 9, 11 and 13 respectively-).

