#Chapter 2: Architecture

The architecture of the application is compose by a set of  modules  specified around the entities that make up the application and a set of directives for viewing and configuring models. Thus, you can define the following modules:

1. **User**, module for managing users with administration permissions and normal users. Similarly it manages the associated authentication of users, and functionalities such as email change, password, account deletion, etc.

2. **Project**, module for managing projects which have a series of users in different roles (administrator, configurator and/or modeler), in addition to a set of artifacts (for example, feature models).

3. **Artifact**, for handling different models to edit and manage (models features and product configurations), entities that have a number of basic characteristics of validity and belonging to a particular project, which are accessed by connecting to the server that contains the solvers developed by the [TiCSW group](http://ticsw.uniandes.edu.co).

4. **Directives**, for the management of the different directives that are used in the application for displaying models features (display and configuration).

Each of these modules has a set of elements to fulfill its function such as controllers, services and HTML templates. This organization was determined searching for the project to be cohesive but loosely coupled, and the structure to be simple to understand.  

On the other hand, the web application developed communicates through a REST service of solvers. Thus the services associated with the visualization and configuration features models communicates to the server where the validation logic is.