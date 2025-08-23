### Spring MVC and MVC in general
* Classically the goal of the **MVC(Model-View-Controller)** pattern was to delegate different kinds of tasks to different
kinds of objects of some specific types of Classes. These tasks were divided into **Model** which compartmentalized the entities
that were directly connected to the Business logic. For e.g. in a parking lot system, few models could be Parking lot itself, 
Ticket, Lot number etc. They are the blueprint for the objects which hold the information of the state. For e.g. the Ticket might
have some attributes like Ticket No., Date, CarType, parkingLotLocation etc. 
* The **Controller** is responsible for accepting the input and then changing the state of the objects, i.e. making changes to the
attributes of the objects(Models). Then the Model conveys those changes to the **View** via the network and the View then responds to 
the changes.
* In the traditional structure, this connection to View was continuous. This followed the **Observer Pattern** where there are
**Subscribers**, and they are subscribed to **Publishers** who are the source of the changes. The subscribers, View in this case, respond
to the changes and changes the layout of the pages. But later in the Spring MVC, the connection was deliberate via **HTTP** calls and there
was no need of maintaining the continuous connection. This was because the traditional MVC was followed for applications run on the local
machines where the objects shared the same memory space whereas Spring is used for web applications, hence there was a move to distributive
which made the move to HTTP calls natural.

##### Spring MVC
In the modern sense, the spring applications don't have the logic for the maintenance of the View in the same repo as the controller and the
models. Because the requests are now stateless, there is a need of persistent memory to store the info of the model states. This is the 
**Repository** layer and there sits a new layer called **Service** later which takes the request from the controller, gets/modifies the data
in the Repository(database) and delivers the results to the controller. Then the controller use a **Data Transfer Object(DTO)** to transfer the 
changes to the front-end which is connected to the back-end(Spring Application) via an API. 

