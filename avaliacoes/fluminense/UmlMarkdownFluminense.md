```mermaid
classDiagram

class matchController {
    +  doGet(HttpServletRequest, HttpServletResponse)  void 
    +  doPost(HttpServletRequest, HttpServletResponse)  void
}

class Team {
    - name : String
    - colors : String
    - players : List<Player>
}

class Match {
    - home : Team
    - visitor : Team 
    - homeScore : int
    - visitorScore : int 
    - date : Date
    + getResult() Team
    + getResult(t : Team) int 
}

class Player {
    - name : String
    - surname : String
    - number : int
    - position : String
}
Team "1" o-- "*" Player : players
Match "1" o-- "1" Team : home
Match "1" o-- "1" Team : visitor