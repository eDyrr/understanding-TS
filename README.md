# understanding-TS

my humble attempt to understanding some of TS's concepts:

## `async/await`:

to understand `async/await` we need to understand `promises` first.

### promises

In `typescript` promises are a mechanism which allows for code to run whilst waiting for a certain task to be done.

We make a `promise` when trying to return some kind of value, at the beginning, a `promise` is pending, yet at the end it is going to be settled either by being resolved or rejected.

The body of a `promise` has to determine when a `promise` **is resolved** or **isn't**.

When a `promise` is **resolved**, we handle it with the `.then()` function, and when its not **resolved**, i.e **rejected** we use the `.catch()` function.

an example (from Fireship), is when you book an Uber, the driver makes a `promise` to come and pick you up, *if he comes*, the promise is fulfilled *then* you go ahead and take your ride, but if he doesnt then you *catch* another ride.

here's a humble implementation:

```
const ride = new Promise<void>((resolve, reject) => {
    if(uber.arrived) {
        resolve() ;
    } else {
        reject() ;
    }
}) ;
```

and here's the *consumer* code:

```
ride.then(() => {
    getIn() ;
}).catch(() => {
    takeAnotherUber() ;
}) ;
```