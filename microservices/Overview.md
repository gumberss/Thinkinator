
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
