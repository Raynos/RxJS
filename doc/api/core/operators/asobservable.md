### `Rx.Observable.asObservable()` [&#x24C8;](https://github.com/Reactive-Extensions/RxJS/blob/master/src/core/linq/observable/asobservable.js "View in source")

Hides the identity of an observable sequence.

#### Arguments
1. `args` *(Array|arguments)*: Observable sources or Promises competing to react first either as an array or arguments.

#### Returns
*(`Observable`)*: An observable sequence that hides the identity of the source sequence.

#### Example
```js
// Create subject
var subject = new Rx.AsyncSubject();

// Send a value
subject.onNext(42);
subject.onCompleted();

// Hide its type
var source = subject.asObservable();

var subscription = source.subscribe(
    function (x) {
        console.log('Next: ' + x);
    },
    function (err) {
        console.log('Error: ' + err);
    },
    function () {
        console.log('Completed');
    });

// => Next: 42
// => Completed
```

### Location

File:
- [`/src/core/linq/observable/asobservable.js`](https://github.com/Reactive-Extensions/RxJS/blob/master/src/core/linq/observable/asobservable.js)

Dist:
*TBD*

Prerequisites:
*TBD*

NPM Packages:
- [`rx`](https://www.npmjs.org/package/rx)

NuGet Packages:
- [`RxJS-Complete`](http://www.nuget.org/packages/RxJS-Complete/)
- [`RxJS-Main`](http://www.nuget.org/packages/RxJS-Main/)

Unit Tests:
- [`/tests/observable/asobservable.js`](https://github.com/Reactive-Extensions/RxJS/blob/master/tests/observable/asobservable.js)
