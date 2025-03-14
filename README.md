#### Remote repo on Github: `https://github.com/uldahlalex/fs25_11_2`

### Agenda
- 08:15: Introduction To Exercise 1
- 08:30: Exercise 1
- 09:15: Follow-up on Exercise 1 + Introduction to Exercise 2
- 09:30 - 10:45: Exercise 2
- 10:45 - 11:00 Wrapping up exercise 2
- 11:00 -> Workshop

## Exercise 1: Multi-API Backend with shared authentication

Expand on the onion you started building last time.

Make a single ISecurityService + SecurityService capable of issuing JWT's. Both can be in the Application Layer of your onion. Make sure:
- REST API can trigger the method to issue a token to the client. (Log in / register)
- REST API can verify a token attached to an HTTP request (in the Authorization request header). (Some protected action)
- Websocket API has event for issuing a token (like a ClientWantsToSignIn Dto + Event Handler)
- Websocket API has "protected" event where JWT in the DTO is verified by the SecurityService

*(Tip: You can simply use the super simple JWT authentication from here: `https://github.com/uldahlalex/fs25_5_2/blob/main/ExerciseCSolution/SecurityService.cs` and add the Nuget package "JWT")*


#### Success criteria:

## Exercise 2: Multi-API Backend with a single ConnectionManager

Now each API should be capable of using the same IConnectionManager **from the Application Layer**. The concrete class implementing the IConnectionManager should exist in the **infrastructure layer**.

#### Success criteria:
When sending an HTTP request you should be able to trigger a broadcast to clients connected using websockets.