this file acts as the designing and planning of the required assigment, #2 AI vehicle search

deadline: within 5 days of receiving the form

that translates to 18, or 17 to be comfortable as the submission date, even prior can be submitted as soon as the system is created

Planning:
the service needs to be well scoped and decisions are to be made clearly, or else the deadline will be missed
as such the following is decided

- to try out a new system that can provide best results if it works and optimise it
- to also have a fallback system in the works in case the newer system cant fully function within deadline
- optimisations to the newer plans are to be kept to a minimum

service scope:
from the problem statement: "Al Vehicle Search Engine Build a backend service where users search a vehicle catalogue using natural language. Examples: "Show SUVs under {15L" "Diesel automatic cars below 80k km" 'Family cars with high safety ratings"

this translates to NLP input -> searching over datasets -> presenting search results

the first problem is of dataset sourcing

the second problem is of filtering through the dataset when and as obtained, also, we are to account for missing values and incomplete lines among it

following that, implementation of ai system itself: it must be lightweight, able to parse through the data cleanly, match requirements and be very very fast
thankfully, a system as this already exists: system one models, laya can be loaded in and then served via hf transformers

for scaling the system to customers, another problem is run into: to optimise for concurrency, or for resiliency, which is where a scoping decision is made, to be able to serve 10k+ users concurrently

for this, go is the best suitable language to create the service apis

however, the questions also come for: security, safety, and for portability
portability here refers to the services ability to connect to already existing infrastructure, while having or adding the least amount of foot print of its own

uber created a mcp gateway service for its internal use to ensure that all teams and systems could connect from one space and run from it, and a tool in one team was not patched together, or another tool wasnt inaccessible to another team

given indias realistic climate of 'patched' services, this service should then be connected as a microservice in a node runtime
security then itself, can be ported to node with it

another scoping decision is regarding the response type for the model: that can only be answered by testing the service if the system should respond with a id of the vehicle it found, which then another search provides the full info to the user, or with the full details of the vehicle in the dataset

technical debts:


time wise schedule:

Day 1:
 - obtain datasets
 - run model tests 
 - initialise templates for service architecture

 Day 2:
 - integrate the model and service
 - check for architecture issues
 - run tests on the service

Day 3:
- finalise service decisions
- run the service itself
- final polishes

this concludes the plan scoping and current decisions made for the problem statement
