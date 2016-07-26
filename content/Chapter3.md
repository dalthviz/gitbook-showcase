#Structure Data

Based on documentation of [Firebase](https://firebase.google.com/docs/database/web/structure-data) for structuring data, the database must be built compactly (avoiding nesting). Thus, the information is structured in such a way that the entities are store in a collections (an array) en the root of the database. The relationships between entities are handled with references using for a key the identification of the element in the correspondent list (_artifacts_, _projects_, or _users_), and the value true.

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
In the JSON, note that the _artifacts_ are in an array in th root of the tree. Also, there is an artifact identify **UIDArtifact**. In the same way, the _projects_ are in another array called _projects_ in the root of the tree. There is a project identify with **UIDProject**. This project has an artifact list. In this project, there is an entry where the key is the same as the artfact mentioned above (**UIArtifact**) and the value is true (line 10). Note that a similar relationship between the aforementioned project, and the user with identification **UIDUser**, exists (in the user projects list -line 21- and  in the administrators, configurators and modelers lists of the project -lines 9, 11 and 13 respectively-).

In this example, the Project has an array with the keys of the artefacts. The data of each artifact are in another array. If you want to get the data of the artifacts that are part of the project, is necessary load the data of the project, check for the elements of the array and search for each of the artefacts separately. Next, and example code using Javascript and the API of Firebase:

```javascript

// Gets the reference to a project
var ref = firebase.database().ref().child('projects')
                                .child('UIDProject');

// Each of the values of the list of artifacts gets charged
ref.child('artifacts').on('child_added', function(snapshot) {
 
    // Gets the key of the artifact
    var idArtifact = snapshot.key();
    
    // Gets the reference (URL) to the data of the artifact
    var refArtifact = firebase.database().ref().child('artifacts')
                                                .child(idArtifact); 

    // Prints in the console the data
    refArtifact.once('value', function(artifact) { 
            console.log(artifact.val()); 
    }); 
});

```
  
