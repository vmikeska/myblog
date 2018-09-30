Title: Why you should never evaluate conditional statements inline
Published: 26/9/2018
Tags: 
- refactoring
- software architecture
---
The conditional statement, conditional expression, conditional construct or commonly known the IF - a fundamental feature of every programming language.

Its right usage doesn't bring benefits just only to you, but also to all the other people participating in the project. Even the programmers whose seniority cannot be put in doubts can author a line of code like this:

```typescript
if (this.carType === 'Truck' && (this.state === this.acitveState || this.item === this.selectedItem)
    && _.find(this.itemList, {state: 'active'}) && this.year > 2000)
{
```
What is wrong with such a line of code? Well, basically everything. It's difficult to read, maintain, debug, refactor or generally make sense of it.

Consider following dummy code:

```typescript
public execute1() {
        //here would be typicaly placed a comment trying to describe what
        //is going on in this crazy IF
        if (this.carType === 'Truck' 
            && (this.state === this.acitveState || this.item === this.selectedItem)
            && _.find(this.itemList, {state: 'active'}) && this.year > 2000) 
        {
            this.updateCar();
            this.saveCar();
            this.broadCastUpdates();
        }

        //executing evaluations methods in the if statement is a very bad
        //practice. it's practically undebuggable and if you use it again 
        //in the IF body as a parameter, it might return another value
        if (this.notificationRequired() && this.matchNotificationRules() 
            && this.canNotify())
        {
            this.notifyGroup(this.canNotify());
        }

        //this line is maybe not so long and unclear, but doesn't provide 
        //the actual information to the reader, why is the condition 
        //passing or not
        if (['VW', 'AUDI'].includes(this.brand)) {
            this.notifyConcern();
        }
    }
```

In an entry like this `year > 2000` is obvious that to pass the evaluation, the `year` must be higher than `2000`. And this is exactly the only information provided by the entry.

The best way how to provide such a information is to encapsulate the evaluation logic into a named method or assign it into a property.

When a user sees something like `let isNotAnOldtimer = year > 2000;`, he is aware that to pass the evaluation, the car must not be an oldtimer. That is significantly more beneficial to the consumer of the method than the plain `year > 2000`.

So let's begin the refactoring by splitting the excessive conditional statements into several short logical parts and give them a name.

```typescript
public execute2() {
        //each of these evaluations has one single named results
        //it introduces some new lines to the code, but brings
        //some more sense into it
        let isTruck = this.carType === 'Truck';
        let isActive = this.state === this.acitveState;
        let isSelected = this.item === this.selectedItem;
        let hasItem = !!this.carList.find(this.itemList, {state: 'active'});
        let isNotAnOldtimer = this.year > 2000;

        let canUpdateCar = isTruck && (isActive || isSelected) && hasItem && isNotAnOldtimer;
        if (canUpdateCar)
        {
            this.updateCar();
            this.saveCar();
            this.broadCastUpdates();
        }
        
        //evaluate methods outside the condional statement is a must.
        //you should also consider properties (gets), if you use them in the
        //method body. Their value might change during execution
        let isRequired = this.notificationRequired(); 
        let matchesRule = this.matchNotificationRules() 
        let canNotify = this.canNotify();

        let shouldNotifyGroup = isRequired && matchesRule && canNotify;
        if (shouldNotifyGroup) {
            this.notifyGroup();
        }

        //it's better to encapulate even such a single evaluations
        //the statement might be clear to you, but doesn't have to be
        //clear to the others
        let belongsToConcern = ['VW', 'AUDI'].includes(this.brand);
        if (belongsToConcern) {
            this.notifyConcern();
        }
        
    }
```
Now when it has been broken into the several lines, each of them representing one single block of logic, we can read in it like in a book.
You can literally read what is going on in there and while debugging, comfortably step line by line and see the result of each block.

The new code we introduced during the refactoring might give you an excessive impression. And yes, you are most possibly right.
But our refactoring is not over yet.
One, two, maybe three lines we could keep, but when this threshold reached, the code should be encapsulated into a well-named method.

```typescript
public execute3() {
        //after we put it all into a well name method, user can immediately 
        //see why this condition has passed or not
        let canUpdateCar = this.canUpdateCar();
        if (canUpdateCar) 
        {
            this.updateCar();
            this.saveCar();
            this.broadCastUpdates();
        }

        //while debugging, it really helps to find the bug quick
        let shouldNotifyGroup = this.shouldNotifyGroup();
        if (shouldNotifyGroup) {
            this.notifyGroup();
        }

        //well, no more work to be done in this one-liner, it's short and clear
        let belongsToConcern = ['VW', 'AUDI'].includes(this.brand);
        if (belongsToConcern) {
            this.notifyConcern();
        }
    }

    private canUpdateCar() {
        //inside of this encapsulation is then possible to find what exactly
        //is wrong
        let isTruck = this.carType === 'Truck';
        let isActive = this.state === this.acitveState;
        let isSelected = this.item === this.selectedItem;
        
        let item = !!this.carList.find(this.itemList, {state: 'active'});
        let isNotAnOldtimer = this.year > 2000;

        let canUpdateCar = isTruck && (isActive || isSelected) && hasItem && isNotAnOldtimer;
        return canUpdateCar;
    }
    
    private shouldNotifyGroup() {
        let isRequired = this.notificationRequired(); 
        let matchesRule = this.matchNotificationRules();
        let canNotify = this.canNotify();

        let shouldNotifyGroup = isRequired && matchesRule && canNotify;
    }

```

However, there can't be found anything wrong, I admit a was a bit wordy programmer in this example.
But if you manage to stick to this rule for maybe 80-90% of your code, it brings some seniority into your outputs.

## Summary
It's necessary to realize that code you input is not made exclusively for you. You should turn your geeky infinite one-liners into something that makes sense to the future consumers of your code.

Let's go once more through and point out the major benefits.

### Better sense of the code
The user should be able at first sight find out what's the logic flow in your methods. In order to achieve that, naming and encapsulating values inputting the conditional constructs is a must.

### Easier debugging
It's always a bit tricky to deal with bugs, but well written conditional constructs help to find them. Bugs are not always being made just on the technical level, they occur on the level of business logic as well. Therefore when dealing with well named and formatted code, to fix your business logic is much easier.

### Self-documenting code
Encapsulation and right naming produce self-documented code. With such a code is much easier to drag other developers without a deep project knowledge into the project.

### Solid fundament for future refactorings
Well encapsulated and named code gets you rid of the hassle you might face when the time of refactoring comes. Before you begin to shift your code over the application, it's always better to start with an instant overview about the happening in there.