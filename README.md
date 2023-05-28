# (SW_TJV) Semester work on the subject of Java Technology

# Requirements
Semestral project is a client–server application working with at least 3 domain types that implements full CRUD (operations create, read, update, delete) over all of them.

## Server part
It is a three-layer application (persistence layer, business/application layer, and presentation layer (REST API): **hard requirement**):

1. uses Spring Framework and written in Java programming language (hard requirement; another JVM language may be approved: ask the tutor)
2. uses object-relational mapping (ORM) in persistence layer
    - the data tier must use a relational database system that uses a persistent data storage and is capable of serving concurrent requests       (a DB server): otherwise loss of 2 pts
    - neither in-memory DB nor an embedded DB (e.g., SQLite) is not an option
    - while meeting these criteria, the RDBMS is the student’s choice
3. at least three entities with at least one many-to-many association (implies at least four tables in the database)
    - loss of 4 pts without a working many-to-many association
    - implements complete CRUD over all entities and also over the M:N association
    - at least one complex query (besides CRUD or working with M:N association; thus multiple tables should be involved) in ORM (using             JPQL); otherwise loss of 4 pts
4. contains clearly separated business layer
    - implements all data operations enabled by persistence layer (using delegation)
    - uses transactions in a reasonable way
    - loss of 0.5 pt for any non-working operation
    - loss of 5 pts for each case of improper layering
5. contains clearly separated layer of RESTful web service (REST API)
    - exposes all business operations and supports all entities; loss of 2 pts for each non-working operation
    - follows web standards (designing and implementing standardized REST API is important here); loss of 1 pt for each working and not           RESTful operation
    - does not return HTTP status 500 for invalid requests (i.e., the service is bug-free, status 500 is used only for server problems,           e.g., DB connection); loss of 1 pt for each case of HTTP status breaking standards
    - complete and machine-readable API documentation (e.g., OpenAPI): all endpoints, operations, and data formats; loss of up to 2 pts for       missing or poor quality API documentation
6. contains automated tests
    - three different types of tests taught in this course; loss of up to 4 pts for missing type of test or for test of poor quality
7. uses smart build (Gradle); automated tests should be run and evaluated within the build system
8. is developed using the git versioning system
    - Gitlab FIT repository (gitlab.fit.cvut.cz/<username>/<server_repo>) should be used for both development and submitting
  
## Client part
It is an application written in any programming/scripting language with the following features:

1. any user interface (web, GUI, interactive console application)
2. uses the REST API of the server part as the backend
3. implements a complex business logic operation over the server part (this business operation needs to be approved by the tutor until checkpoint 1, see below)
    - the business operation is a single action that is composed of multiple data operations (CRUD); the client issues these data operations     by multiple calls on the server part
4. is versioned
    - loss of 15 pts for non-working complex operation
    - Gitlab FIT repository (gitlab.fit.cvut.cz/<username>/<client_repo>) should be used for both development and submitting
5. loss of 20 pts for missing or very poor client application
