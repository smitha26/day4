# day4
Inheritance?
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
