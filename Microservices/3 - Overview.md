
# Things to think about
  -  Authentication
   - Logs
   - Security
   - Comunication synchronously or asynchronously
   - Authentication to use
   - Template project
   - context creation should be transient or scoped
   - CI / CD
   - Team comunication

# Why microservice:

##    Monoliths:
   ### Prós:
   #### Good for small:
   - applications
   - teams
   - quantity of users
   - quantity of data
   - quantity of modules
### Cons:
 #### For big applications:
   - Generate too many technical debts
   - Generate entangled modules (one depends another one)
   - Difficult to maintain
       - Deploy:
           - One single line of code changed, the entire application must be deployed
           - Risky
           - Requires downtime
       - Difficult to scale (Difficult **is not impossible**):
           - Horizontal scaling often not possible
           - Vertical scaling is expensive:
               - Operador database server must have 128Gb of Ram memory ans 16 Xeon processor cores to process in the worst case (example)
           - Whole application must be scaled:
               - If one process require memory and we set it, all the application will get a part of it, even it doesen't need it
       -  Forced to use the same tecnology:
           - Difficult to test new tecnologies
           - if a new tecnology is delivered to solve a problem we heve, we won't be able to use
               - reduce agility to:
                   - Difficult to adopt new patterns and practies that benefits our application
           - new features require changes everywhere
           - Long training requirements
           - crushed under trafic needs
           - Failure to adapt to innovations
               - Lost good developers, because they don't want to work with old tecnologies

## Microservices:
   - has a clearly defined boundary with a public interface and the data can be accessed only by that public interface
   - Organize microservices around **business** capabilities
   - Each microservice has its own database
   - Accelerates the velocity of software development by **enabling small, autonomous teams to work in parallel** (*for me, this is the best reason to use microservices*)
   - Requires DevOps and small, autonomous teams
   - Better choice for large and complex applications
        ### Prós:
        - Resilience
        - Each microservice:
            - can be owned by a time
            - easier to understand
            - can be rewritten very often if necessary
        - Tecnology Choice:
            - Adopt new tecnology that help us face our problems (**Use data to chose, do not use a tecnology because the hype, please**)
            - Flexibility to find and use the right tool (one microservice can use relational database and other can use document database)
        - Deploy:
            - Individual deployment (low risk)
            - minimize downtime
            - frequent updates
                - we can get a high priority issue, solve and deploy imediately
                - it can be make a lot of times a day
        - Scale:
            - can scale each microservice individually
                - Cost-effective
        Agility:
            - Adapt quickly to business changes
            - Easly to reuse microservices in new scenarious       
        #### Cons:
        - Developer Productivity working on the entire: 
            - will you download, configure each one and run all the microservices?
                - bit time consuming
            - Complex interactions:
                - hard to understand the behavior of the whole system 
        - **Automated tests are not an optional approach**:
        - **Automated deployment are not an option approach**:
            - too many microservices
        - Monitoring:
            - You won't want to connect individually to each microservice to get the logs 
            - need to centralized place to chec logs and monitoring of problems
    not allow:
        - share same data store with other microservice
    Limitations:
        - Eventual consistency (Temporary inconsistency)
        - Database Joins
            - Define service boundaries well minimize the need to aggrefate data
        - Transactions
	        - usually you need to compensate a event that was processed and an error occured on the next event
            
        #### Contracts:
        - if you change only one microservice, you can deploy this only one
        - if you change the public interface of this microservice, **you can make a break change**, and must update all the clients of this microservice.
        - To void break changes:
	         - Create contract tests
            - if it is possible, make only additive changes:
                - new endpoints
                - new propertie on DTOs
            - if it is not possible to avoid :
                - introduce version 2 of the API and still suporting version one
                    - easly forgotten in development. To Avoid:
                        - make individual teams responsible for each microservice
                        - add the new capability 
                        - deploy the updated microservice
                        - later, update clients
                        - add tests to the previus version API
                            - automated, runing as part of CI build process
                            - if the tests fail, everyone is aware that there's a problem with a compatibility
    share codes between microservices:
        - avoid to share code that force all microservices update
        - it is not allowed to share business logic
                
#### Avoid:
   - circular dependencies 
   - chatty communications (frequent comunication between one with other)

How to evolving to microservice:
- Some people argue to avoid start a new project using microservice
- Add new feature as a microservice 
- decompose a monolith:
	- extract microserivce
     - define:
        - responsabilities
        - public interface
	
#### how to break our system into microservices:
- identify loosely coupled components
- identify database seams ( junção, ligação, acoplamento)
   - are there certain groups of tables that conceptually belong together?
       - identify all the places in the code that read and write from those tables. They can be extracted to form a microservice
- identify bounded contexts
- sketch your ideas on a whiteboard
   - run them through real-world use cases and see witch services would be involved
   - that can help you identify potential problems if too many services are required to colaborate together to achive a single business capability 
