Design Patterns:
Builder Pattern
situation: multiple complex object, even if I don't need some parameter I would still need to specify them in the constructor call

    class Address {
      constructor(zip, street) {
        this.zip = zip
        this.street = street
      }
    }   

    class User {
      constructor(name, age, phone, address) {
        this.name = name
        this.age = age
           this.phone = phone
        this.address = address
  }
    }

    const user = new User('Bob', undefined, undefined, new Address('12345', 'Main St.'))

 solution:
        class Address {
  constructor(zip, street) {
    this.zip = zip
    this.street = street
  }
}

class User {//object as second parameter, if no argument object with nothing {}. if i wanna put a defalt value in object I put value as dimostrated in phone
  constructor(name, { age, phone = '123-456-7890', address } = {}) {
    this.name = name
    this.age = age
    this.phone = phone
    this.address = address
  }
}

Facade Pattern:
Goal is to make it easy to change code in future, especially where we use api calls

