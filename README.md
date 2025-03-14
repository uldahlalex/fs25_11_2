#### Remote repo on Github: `https://github.com/uldahlalex/fs25_11_2`

#### Slides: `https://docs.google.com/presentation/d/1_g3QGOAxs3ZtORgvmrJDWplIK1rL2o3AUd28XAKExig/edit?usp=sharing`

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

### Help
If you just want to see how to make an IConnectionManager without any infrastructure or API references, I have made one here:

`https://gist.github.com/uldahlalex/bc968f5f44b68d62d5b82df07bab823f`

Here's an example of a concrete dictionary based connection manager implementing the above interface:

`https://gist.github.com/uldahlalex/0222e2ab7249bd9ca13a7d40e711345f#file-gistfile1-txt`
