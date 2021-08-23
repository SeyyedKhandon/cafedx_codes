# Use meaningful and pronounceable variable names

```javascript
// bad
// current date
const yyyymmdstr = moment().format("YYYY/MM/DD");
// elapsed time in days
const d = 20;

// good
const currentDate = moment().format("YYYY/MM/DD");
const elapsedTimeInDays = 20;
```

```typescript
// bad
class DtaRcrd102 {
  // A class for customer
  private genymdhms: Date;
  // generation date, year, month, day, hour, minute and second
  private modymdhms: Date;
  // modification date, year, month, day, hour, minute and second
  private pszqint = "102";
  /* ... */
}
// good
class Customer {
  private generationTimeStamp: Date;
  private modificationTimeStamp: Date;
  private recordId = 102;
  /* ... */
}
```

# Use the same vocabulary for the same type of variable

```js
// bad
getUserData();
getUserInfo();
getUserRecord();
getUserProfile();
getClientData();
getClientInfo();
getCustomerRecord();

// good
getUser();
```

# Use searchable names

```javascript
// bad
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);

//good
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;

setTimeout(blastOff, MILLISECONDS_PER_DAY);
```

```js
// bad
let s = 0;
for (let i = 0; i < 34; i++) {
  s += (t[i] * 4) / 5;
}

// good
const REAL_DAYS_PER_IDEAL_DAY = 4;
const WORK_DAYS_PER_WEEK = 5;
const NUMBER_OF_TASKS = 34;
const sum = 0;
for (let i = 0; i < NUMBER_OF_TASKS; i++) {
  const realTaskDays = taskEstimate[i] * REAL_DAYS_PER_IDEAL_DAY;
  const realTaskWeeks = realTaskDays / WORK_DAYS_PER_WEEK;
  sum += realTaskWeeks;
}
```
