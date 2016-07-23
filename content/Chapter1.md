# Chapter 1: Requirements

The software to be developed is a web application that allows users to:

1. **Edit feature models**, and

2. **Configure products** according to these feature models.

Each user could have their own models, independent of which have other users. Will be possible for a user to share their models. A user could edit and / or configure their own feature models or the ones he has access. 

Additionally, it is expected that the application enable managers to:

1. **Manage users of the application**, including options for
authenticate users and allow sharing models, and

2. **Control of Versions** of different models and configurations.

Ahead on detail, the modules of the system are presented.

###1.1 Edition of feature models

Each user will be able to:

1. **See a list of feature models** own or to which
have access. Models must be associated with a user
_owner_. The owner could share models so that other users can edit, configure them or do both.

2. **Edit feature models.**
   
    * Add, or Delete feature models.
    * Add, Remove, Edit attributes of feature models.
    * Moving parts of tree to another.
    * Add, Remove, Edit constrains.  
       
3. **Validate feature models.** Determine if the model does not has errors, e.g., that the model is a valid one, that does not have dead characteristics, or does not have contradictory constraints.

###3.2. Configuration of Products

Each user also to be able to:

1. **See a list of models that can be configured**, either
that they are of the user or he has access to these models.

2. **Start the configuration of a product** from a model.
    * **Select or de-select a characteristics.** The system should propagate decisions and select or deselect the characteristics according to appropriate restrictions.
    * **Prefer or not prefer one characteristic.**
    * **Undoing a decision** (selection, de-selection, preference or not preference)
    * **Auto-complete a configuration.**
3. **Resume configuration process of a product.** Restarting the process at the point where it was the last time.

###3.3. User Management

Each user will be able to:

1. **Log In in the application.**  

2. **Change his personal details.**  

3. **Change Password.**  

Additionally, a _admin user_ will be able to:

1. **Create or Edit users.**

2. **Change password of a user.**

###3.4. Version control

Each user will be able to:

1. **View the version history of a Model.**

2. **See the version history of a Configuration.**
