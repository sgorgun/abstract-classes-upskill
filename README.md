# Vehicle Calculates Tolls System 

Intermediate level task for practicing pattern matching, object-oriented programming, Decorator design pattern.

Estimated time to complete the task - 2h.

The task requires .NET 6 SDK installed.

## Task Details

- Complete [Tutorial: Use pattern matching to build type-driven and data-driven algorithms](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/tutorials/pattern-matching)

- Answer the following questions:
   - What are the main pattern matching scenarios?
   - Why this approach is used to solve the problem above?

   _Discuss it with your trainer, if you work in a regular group._

- Using the classic object-oriented design solve the following problem:
   Create the types that prepresent vehicle types `Car`, `Taxi`, `Bus`, `DeliveryTruck` for calculate tolls to manage peak time traffic. Pricing depends on     
   - vehicle type;
   - the number of occupants in the vehicle;
   - on the time and the day of the week.

   <details>
   <summary>

   The basic toll calculations

   </summary>
   
   The most basic toll calculation relies only on the vehicle type.    

   _For tests:_

   | Vehicle | Basic toll |
   | ------ | ------ |
   | Car | $2.00 |
   | Taxi | $3.50 |
   | Bus | $5.00 |
   | DeliveryTruck | $10.00 | 

   </details>

   <details>
   <summary>

   Adding occupancy pricing

   </summary>

   The toll amount adjusting for the vehicles to travel depeneds on the passenger count. The movement of vehicles with maximum capacity is encouraged.       
      - сars and taxis without passengers pay some amount extra;   
      - for cars and taxis, the discount depends on the number of passengers;    
      - for buses, the amount of the discount depends on the percentage of filling.      

   _For tests:_

   **Car and Taxi**

   | Passengers count | Extra/discount |
   | ------ | ------ |
   | 0 | extra $0.50 |
   | 2 | $0.50 discount |
   | 3 and more | $1.50 discount |

   **Bus**

   | Passenger filling in % | Extra or discount |
   | ------ | ------ |
   |  less than 50% | extra $2.00 |
   | more than 90% | $1.00 discount |
   
   The toll amount adjusting for the delivery trucks depends on its weight: for trucks over a certain weight, an additional fee is charged, otherwise a discount is provided.
   
   _For tests:_    

   **Truck**

   | Weight class | Extra or discount |
   | ------ | ------ |
   | over 5000 lbs | extra $5.00 |
   | under 3000 lbs | $2.00 discount |

   </details>

   <details>
   <summary>

   Adding peak pricing

   </summary>
   
   Finally, peak hours are added to the pricing. For example, in the morning and evening hours, the tolls are increased. The rule by which the cost is recalculated in this case may depend on the direction of movement (from the city / to the city).

   _For tests_

   |   Day	   |     Time   	| Direction |	Premium |
   |-----------|--------------|-----------|----------|
   | Weekday	| morning rush	| inbound	| x 2.00   |
   | Weekday	| morning rush	| outbound	| x 1.00   |
   | Weekday	| daytime	   | inbound	| x 1.50   |
   | Weekday	| daytime	   | outbound	| x 1.50   |
   | Weekday	| evening rush	| inbound	| x 1.00   |
   | Weekday	| evening rush	| outbound	| x 2.00   |
   | Weekday	| overnight	   | inbound	| x 0.75   |
   | Weekday	| overnight	   | outbound	| x 0.75   |
   | Weekend	| morning rush	| inbound	| x 1.00   |
   | Weekend	| morning rush	| outbound	| x 1.00   |
   | Weekend	| daytime	   | inbound	| x 1.00   |
   | Weekend	| daytime	   | outbound	| x 1.00   |
   | Weekend	| evening rush	| inbound	| x 1.00   |
   | Weekend	| evening rush	| outbound	| x 1.00   |
   | Weekend	| overnight	   | inbound	| x 1.00   |
   | Weekend	| overnight	   | outbound	| x 1.00   |

   </details>
