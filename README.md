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

Observer pattern
Observer pattern offers a subcription models in which object subscribe to an event and gets notified when the event occurrr

class Subscriber{
    constructor(){
        this.subscribers=[]}
     subscribe(fn){
         this.subscribers.push(fn)}
     unsubscribe(fn){
         this.subscribers=this.subscribers.filter((item)=>{item != fn})
    broadcast(data)//or fire{
        for(let i=0;i<this.subscribers.length;i+ ){this.subscribers[i](data)}}
}
}    
 
 Destructuring:

 work with arrays and objects. Easy way to assign arrays/objects value to propriety, or swap vars

 let demo=[1,2,3,'star']

let ['a','b','c',4]=demo

['a','b','c',4]= [4,'a','b','c']


let demoObj={
    home:0,
    sea:45
}

let {home:renewHouse, sea}= demoObj

