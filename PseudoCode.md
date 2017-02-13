# Hot Restaurant

## Site

* Home Page
  - View Tables
    * List current reservations
    * List waitlist
  - Make reservation
    * Submit Form
      * If sufficient tables, seat customer (add to "current reservations" list)
      * Else add to waitlist
* Link to API

## API

* **POST new reservation**
  - Takes JSON body for new reservation
    - If table available, return true
    - Else return false
* **GET all reservations**
  - Returns all reservations as JSON
    - array of objects
* **GET all waitlist**
  - Returns all waitlisted reservations as JSON
    - array of objects
* PATCH (update) waitlist
  - Takes JSON body for current reservation
    - Updates reservation with values in object
* PUT (replace) waitlist
  - Takes JSON body
    - Replaces entire reservation object with new one
* DELETE from reservation
  - Key as parameter in URL
  - Deletes currently seated reservation
  - If customers on waitlist
    - Pop customer from top of waitlist
    - Add to reservation list
    - Return JSON object of customer moved from waitlist
  - Else return true
* DELETE from waitlist
  - Key as parameter in URL
  - Deletes customer from waitlist
