# Arrays Methods

## Datas

```javascript
const companies = [
  { name: "Company One", category: "Finance", start: 1981, end: 2004 },
  { name: "Company Two", category: "Retail", start: 1992, end: 2008 },
  { name: "Company Three", category: "Auto", start: 1999, end: 2007 },
  { name: "Company Four", category: "Retail", start: 1989, end: 2010 },
  { name: "Company Five", category: "Technology", start: 2009, end: 2014 },
  { name: "Company Six", category: "Finance", start: 1987, end: 2010 },
  { name: "Company Seven", category: "Auto", start: 1986, end: 1996 },
  { name: "Company Eight", category: "Technology", start: 2011, end: 2016 },
  { name: "Company Nine", category: "Retail", start: 1981, end: 1989 }
];

const ages = [33, 12, 20, 16, 5, 54, 21, 44, 61, 13, 15, 45, 25, 64, 32];

```
## forEach() Method
```javascript
// Similar

for (let i = 0; i < companies.length; i++) {
  console.log(companies[i]);
}

// forEach()

companies.forEach(function(company) {
  console.log(company);
});

// ES6

companies.forEach(company => console.log(company))
```
## filter() Method
```javascript
// Similar

let canDrink = [];

for (let i = 0; i < ages.length; i++) {
  if (ages[i] >= 18) {
    canDrink.push(ages[i]);
  }
}
console.log(canDrink);

// Filter()

const canDrink = ages.filter(function(age) {
  if (age >= 18) {
    return true;
  }
});

// ES6

const canDrink = ages.filter(age => age >= 18);
console.log(canDrink);
```

### Filter retail companies
```javascript
// Filter retail companies

const retailCompanies = companies.filter(company => company.category == 'Retail');
console.log(retailCompanies);
```

### Get 80s companies
```javascript
// Get 80s companies

const eightiesCompanies = companies.filter(company => company.start >= 1980 && company.start < 1990);
console.log(eightiesCompanies);
```

### Get companies that lasted 10 years or more
```javascript
// Get companies that lasted 10 years or more

const lastTenYears = companies.filter(company => (company.end - company.start) >= 10);
console.log(lastTenYears);
```

## includes() Method
```javascript
/*
The includes() method determines whether one
string may be found within another string,
returning true or false as appropriate.
*/

ages.includes(21);
// expected output: true

ages.includes(18);
// expected output: true
```

## some() Method
```javascript
/*
The some() method tests whether at least one element in the array
passes the test implemented by the provided function.
It returns a Boolean value.
*/

ages.some(age => age < 8);
// expected output: true

ages.some(age => age > 75);
// expected output: false
```

## every() Method
```javascript
/*
The every() method tests whether all elements in the array
pass the test implemented by the provided function.
It returns a Boolean value.
*/

ages.every(age => age > 4);
// expected output: true

ages.every(age => age > 30);
// expected output: false
```

## reverse() Method
```javascript
ages.reverse(); // [32, 64, 25, 45, 15, 13, 61, 44, 21, 54, 5, 16, 20, 12, 33]
```

## concat() Method
```javascript
const arrayOne = [[1]];
const arrayTwo = [2, [3]];

const arrayThree = arrayOne .concat(arrayTwo);

console.log(arrayThree); // [[1], 2, [3]]
```

## map() Method

### Create array of company names
```javascript
// Create array of company names

const companyNames = companies.map(function(company) {
    return company.name;
})
console.log(companyNames);

// ES6

const companyNames = companies.map(company => company.name);
console.log(companyNames);
```

### Create array of company informations
```javascript
// Create array of company informations

const companyInformations = companies.map(function(company) {
    return `${company.name} [${company.start} - ${company.end}]`;
})
console.log(companyInformations);

// ES6

const companyInformations = companies.map(company => `${company.name} [${company.start} - ${company.end}]`);
console.log(companyInformations);
```

## sort() Method

### Sort companies by years of creation
```javascript
// Sort companies by years of creation

const sortedCompanies = companies.sort(function(company1, company2) {
    return company1.start - company2.start;
})
console.log(sortedCompanies);

// ES6

const sortedCompanies = companies.sort((a, b) => a.start - b.start);
console.log(sortedCompanies);
```

### Sort ages
```javascript
const sortAges = ages.sort((a, b) => a - b);
console.log(sortAges);
```

## reduce() Method
```javascript
// Similar

let ageSum = 0;

for (let i = 0; ages.length; i++) {
    ageSum += ages[i];
}

console.log(ageSum);

// Reduce()

let ageSum = ages.reduce(function(total, age) {
    return total + age;
})
console.log(ageSum);

// ES6

let ageSum = ages.reduce((total, age) => total + age);
console.log(ageSum);
```

### Get all total years for all companies
```javascript
// Get all total years for all companies

let totalYears = companies.reduce((total, company) => total + (company.end - company.start), 0);
console.log(totalYears);
```

### Combine Methods
```javascript
// Combine Methods

const combined = ages
    .map(age => age * 2)
    .filter(age => age >= 40)
    .sort((a, b) => a - b)
    .reduce((total, age) => total + age);
console.log(combined);
```