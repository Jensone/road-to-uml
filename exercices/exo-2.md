# Correction

Une plateforme de réservation de salles permet aux utilisateurs inscrits de rechercher une salle, consulter sa disponibilité, réserver une plage horaire, et recevoir un email de confirmation. L'administrateur peut valider ou refuser les réservations.



```mermaid
classDiagram
    class User {
        -String username
        -String email
        -String password
        -Boolean isValidated
        -Boolean isTerms
        -Boolean isBanned
        -DateTime createdAt
        -DateTime updatedAt
        -String role
    }

    class Room {
        -String name
        -String image
        -String description
        -String location
        -Decimal price
        -Boolean available
        -DateTime createdAt
        -DateTime updatedAt
    }

    class Booking {
        -DateTime startDate
        -DateTime endDate
        -Decimal totalPrice
        -Boolean isAccepted
        -Room room
        -User user
    }


User "1" -- "0..*" Booking: fait des
Room "1" -- "0..*" Booking: est dans

```