- when we have at least 2 things that change **state**

- and some other entity wants to know when the data has been changed in those things or in other words when they 
changed state

- one strategy would be to "pull" meaning subscriber has to keep asking the object: "have you changed?"

- this strategy is not so good and have issues with scalability, deciding the frequency, etc.

- instead we want to have a "push" strategy" meaning the object should be responsible for informing the subscribers 
about its own change of state

- terminology: "observable" = "subject" = something that can be observed; "observer" = something that can observe;

- applications: 
  - messaging apps: someone sends a message in a chat, others should get notified
  - ui design (specially forms): based on user input, ui may need to change, data to be fetched may need to change, 
  etc. like search functionality in some online stores
    - libraries that actually implement this:
      - ReactJs (owner: facebook) (one-way binding)
      - AngularJS (owner: google) (two-way binding)
      - KnockoutJS (owner: open-source) (two-way binding)
  - reading sensor data (embedded systems, IOT)
  - game design:
    - sample scenario (in shooting games): when player 1 shoots a coordinate, other players get notified, read the 
    coordinate, if the 
    coordinate is the same as their place (means the bullet has been contacted the player), they should update their 
    own health with 20% less value.  

- UML diagram:

  |IObservable      |IObserver   |ConcreteObservable  |ConcreteObserver | 
  |:----------------:|:----------:|:------------------:|:---------------:|
  |add(IObserver)    |update()    |add(IObserver o)    |update()         |
  |remove(IObserver) |            |remove(IObserver o) |                 |
  |notify()          |            |notify()             |                |
  |===============   |=========   | ================   |===============  |
  |                  |            |* getState()        |* display()    |  

  *: these are just for demonstration. other methods of ConcreteObservable and ConcreteObserver depends on the scenario.
  
  - **relations:** 
    - IObservable **has many** IObserver (to notify them upon update)
    - ConcreteObservable **is an** IObservable
    - ConcreteObserver **is an** IObserver
    - ConcreteObserver **has a** ConcreteObservable (to get data upon update)

 - **key idea: push vs. poll**
   - **poll** 2   verb  [ transitive ] 
     
     1 to ask a lot of people the same questions in order to find out what they think about a subject  
     



