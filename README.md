Class Line:
{
    private: Route-forward: Router
    private: Route-back: Router
    struct Bus_line {
        Bus;
        time;
    }
    private: Buses: vector <Bus_line> 

    Line(Route-forward: Router, Route-back: Router){ 
        //use this constructor can add new line and create UUID for this line:
        //    new Line:
        //        Route-forward: Router
        //        Route-back: Router
        //        Buses: NULL // we can call add_bus function to add bus to vector
        set Route-forward: Router
        set Route-back: Router
        set Buses: NULL
    }

    Function set_Route-forward(Router){
        make changes to router-forward
    }
    Function set_Route-back(Router){
        make changes to router-back
    }

    Function add_line_time_to_bus(UUID,time){
        create a  struct Bus_line, search the bus by using UUID and set the time, push them to "Buses: vector <Bus_line> "
    }
    Function delete_bus(UUID){
        delete bus from Buses
    }
}

Class Stops:
{
    private: Name: Stop address
    private: Code: UUID

    Stops(address){
        // use this constructor can add new Stops
        for example:
            stop address: Glenside 1
            UUID: xxxxxx
    }
}

Class Router{
    private: vector <Stops>
    Router(vector <Stops>){
        //use this constructor can add new router
        vector <Stops> = this.vector <Stops>
    }
    Function change_router{
        allow make changes to Router
    }

}

Class Bus:
{
    Private Bus_ID;
    boolean free: free / not free
    Bus(UUID){
        //use this constructor can create new bus:
        Bus_ID = UUID
        free = true
    }
}



System:
{
    //Initialize 4 vector:
    stops_library = vector <Stops>// this is used to save all the Stops
    router_library = vector <Router>// this is used to save all the routers
    Bus_library = vector <Bus>; // this vector used to save all the Buses 
    lines_library = vector <lines>; // this is used to save all the lines
    
    //create stop
    stop1 = new Stops("glenside1");
    stop2 = new Stops("glenside2");
    stop3 = new Stops("glenside3");
    
    push those stops to vector "stops_library"
    // we can create as many as we want stops and push them in to "stops_library"

    //create router
    router1 = new Router(vector <stop1, stop2, stop3,stop4>)
    router2 = new Router(vector <stop4, stop3, stop2,stop1>)
    
    push those router1, router2 to vector "router_library" 
    // we can create as many as we want routers and push them in to "router_library"

    //create bus
    bus1 = new Bus(xxxxxx)
    bus2 = new Bus(xxxxxx)
    bus3 = new Bus(xxxxxx)

    push those bus1,bus2,bus3 to vector "bus_library"
    // we can create as many as we want buses and push them in to "bus_library"
    // we can delete the buses from library by using UUID

    //create lines
    line1 = new line(router_library[0],router_library[1])
    // we will have a line called line1:
    // Name: line1
    // router_forward: router1
    // router_back: router2
    // Buses: NULL

    line1.add_line_time_to_bus(bus1.UUID, 1PM)
    //struct Bus_line will be created with UUID = bus1.UUID, time = 1PM
    //at the same time the inside bus_library: bus1.free = false
    line1.add_line_time_to_bus(bus2.UUID, 2PM)
    //struct Bus_line will be created with UUID = bus2.UUID, time = 2PM
    //at the same time the inside bus_library: bus2.free = false

    // Name: line1
    // router_forward: router1
    // router_back: router2
    // Buses: <( UUID = bus1.UUID, time = 1PM),(UUID = bus2.UUID, time = 2PM)>
    // when we delete struct bus_line from this Buses, in the Bus_library, boolean free = true.

    If we have multiply lines, inside the system this will displayed:
    // Name: line1
    // router_forward: router1
    // router_back: router2
    // Buses: <( UUID = bus1.UUID, time = 1PM),(UUID = bus2.UUID, time = 2PM)>

    // Name: line2
    // router_forward: router1
    // router_back: router2
    // Buses: <( UUID = bus1.UUID, time = 1PM),(UUID = bus2.UUID, time = 2PM)>

    // Name: line3
    // router_forward: router1
    // router_back: router2
    // Buses: <( UUID = bus1.UUID, time = 1PM),(UUID = bus2.UUID, time = 2PM)>

}