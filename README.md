# Application Transformation Exercise

*WARNING*: This is a beta version of the this exercise. Proceed with caution!

## Task

Setup:
- form teams of 3-4 people
  - try to make the teams cross-functional, so you have technical and business expertise in your team
- add your team to the whiteboard and indicate the desired time slots for
  - Milestone "Cloud Scope" (max. 1 hour after beginning the exercise)
  - Review (towards the end of the exercise, before final presentations)
  
First Phase: Milestone "Cloud Scope" & Backlog
- define the "Cloud Scope" of your application transformation
- sketch a high-level architecture including
  - components to be transformed/migrated
  - integration and interfaces between customer systems, other Paketblitz services, and the new components in the cloud
  - required adjustments/transformations of the PC-WS application
- prepare an initial backlog for the topics you will be working on in the next phase, a list of possible topics is given further below
- present the items above to the lecturers during your chosen timeslot before proceeding to the next phase

Second Phase: "Cloud Evaluation" & Presentation
- work on your backlog
- prepare a short presentation (5-10 minutes) for your fellow students with 3-5 of the following topics:
  - learnings
  - "aha!" moments
  - observations
  - open questions
  - where did we get lucky? where not?
  - risks?
  - demo of running service
  - etc.
- prepare a brief review of the things you worked on for the lecturers and present them in your chosen timeslot (we will mainly focus on the presentation)

## Possible Topics to Work On

- Cloud Evaluation: As a proof of concept, try to get the even more simplified PC-WS (see below) running on a cloud platform of your choice (you may also choose to work with containers, e.g., docker-compose or Kubernetes).
- IT Organization, Operations, and Support including CI/CD and DevOps: How would you organize this? What needs to be done? What do we need to look out for? Principles? Guidelines? Technical aspects?
- TCO Analysis including a closer look at the business case: Calculate/estimate the cost of different variants. What kind of investements are justified? (You may want to combine this with the question below)
- Transformation Estimation including a detailled analysis of the initial transformation: What steps are necessary? What is the required engineering effort?
- The Far Future: Where could the cloud journey lead to? What are some new opportunities we gain after the initial transformation? What further optimizations or even new business cases would be possible?

## The Even More Simplified PC-WS

### Differences to the Service Presented in the Lecture

- Authentication omitted for the sake of simplicity
  - if there is some time left, this is a topic you may want to look into based on your chosen solution
- everything uses REST instead of SOAP
- PostgreSQL instead of Oracle database
- no address verification service
- log data is also shipped via REST instead of SFTP (this part was called "Verrechnung", i.e., billing, in the lecture)
  - however, for the sake of the exercise, please assume that the shell script to ship the logs needs to be used
- the account service has the same role as the LDAP, but also uses REST
  - however, for testing purposes, it is  currently accessible from the internet, this may change again later

### The Services

- PrintCode Web Service: https://github.com/SamuelBucheliZ/bfh-pcws
  - Live demo with mocked external systems at  https://bfh-pcws-mock.herokuapp.com/swagger-ui.html
- Viewer: https://github.com/SamuelBucheliZ/bfh-pcws-viewer 
  - Live at https://samuelbucheliz.github.io/bfh-pcws-viewer/
- Paketblitz Account Service: https://github.com/SamuelBucheliZ/bfh-paketblitz-account-service
  - Live at https://bfh-paketblitz-account-service.herokuapp.com/swagger-ui.html
- Paketblitz Datalog Service: https://github.com/SamuelBucheliZ/bfh-paketblitz-datalog-service
  - Live at https://bfh-paketblitz-datalog-service.herokuapp.com/swagger-ui.html
