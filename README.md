Class Line:
{
    Name: UUID
    <!-- Routes: forward or return -->
    Route: vector <Stops>
    Buses: vector <Bus_line> 
}

Class Stops:
{
    Name: Stop address
    Code: UUID
}

Class Bus_line:
{
    Bus: Bus
    Time: Arrival time at the first stop
}

Class Bus:
{
    Bus-ID: UUID
}

Function add_buses() {
    add bus and create an new UUID for it
}

Function remove_buses(UUID) {
    remove bus and also remove the UUID
}

Function add_stop(){

}

Function add_routes(){

}

Function add_lines(){

}

Function add_line_time_to_bus(){
    
}

System:
{

}