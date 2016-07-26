#Chapter 2: Architecture

The architecture of the application is compose by a set of  modules  specified around the entities that make up the application and a set of directives for viewing and configuring models. Thus, you can define the following modules:

1. **User**, module for managing users with administration permissions and normal users. Similarly it manages the associated authentication of users, and functionalities such as email change, password, account deletion, etc.

2. **Project**, module for managing projects which have a series of users in different roles (administrator, configurator and/or modeler), in addition to a set of artifacts (for example, feature models).

3. **Artifact**, for handling different models to edit and manage (models features and product configurations are the ones currently supported). Each artifact belongs to particular project, and can be accessed by the users that have the corresponding permissions. Also, is processed using a conection to the serve that contains the solvers developed by the [TiCSW group](http://ticsw.uniandes.edu.co).

As a part of the **Artifact** module, a set of directives (components for the user interface) that enables to visualize, configure and edit the feature models and configuration ones. Can be mentioned:

* Directive for the visualization of feature models.
* Directive for the configuration of feature models in tree way.
* Directive for configuration of feature models using a form.

Each of these modules has a set of elements to fulfill its function such as controllers, services and HTML templates. This organization was determined searching for the project to be cohesive but loosely coupled, and the structure to be simple to understand.  

On the other hand, the web application developed communicates through a REST service of solvers. Thus the services associated with the visualization and configuration features models communicates to the server where the validation logic is.