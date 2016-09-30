# day4
Inheritance?
example:
class Car {

    public report() {
        console.log(`Year: ${this.year}`);
        console.log(`Make: ${this.make}`);
        console.log(`Model: ${this.model}`);
    }

    constructor(public year:number, public make:string, public model:string) { }
}


class Truck {

    public report() {
        console.log(`Year: ${this.year}`);
        console.log(`Make: ${this.make}`);
        console.log(`Model: ${this.model}`);
        console.log(`Towing Capacity: ${this.towingCapacity}`);
    }

    constructor(public year: number, public make: string, public model: string, public towingCapacity:number) { }
}

// create a car
let myCar = new Car(2015, 'Toyota', 'Camry');
myCar.report();

// create a truck
let myTruck = new Truck(2016, 'Dodge', 'Ram', 5000);
myTruck.report();
----------------------------------------------------------------------
You don't need  to define each vehicle individulally 
abstract class Vehicle {

    public report() {
        console.log(`Year: ${this.year}`);
        console.log(`Make: ${this.make}`);
        console.log(`Model: ${this.model}`);
    }

    constructor(public year: number, public make: string, public model: string) { }
}


class Car extends Vehicle {
    constructor(year: number, make: string, model: string) {
        super(year, make, model);
    }
}


class Truck extends Vehicle {
    public report() {
        super.report();
        console.log(`Towing Capacity: ${this.towingCapacity}`);
    }

    constructor(year: number, make: string, model: string, public towingCapacity:number) {
        super(year, make, model);
    }
}

// create a car
let myCar = new Car(2015, 'Toyota', 'Camry');
myCar.report();

// create a truck
let myTruck = new Truck(2016, 'Dodge', 'Ram', 5000);
myTruck.report();


Declaring an Interface
=======================
interface INamed { //First 2 letters should be in caps
    name: string;
}
class Hammer implements INamed {
    constructor(public name: string, public weight: number) { }
}

class Computer implements INamed {
    constructor(public name: string, public operatingSystem: string) { }
}

class Hamster implements INamed {
    constructor(public name: string, public age: number) { }
}
function printName(product: INamed) {
    console.log(product.name);
}


// create a hammer
let myHammer = new Hammer('Sledgehammer', 20);
printName(myHammer);
