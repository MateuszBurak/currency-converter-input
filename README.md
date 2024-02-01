# Mateusz Burak - simple currency converter using *input*

## Currency converter - input - April 29th, 2023

[Link to the converter](https://mateuszburak.github.io/currency-converter-input/) |
[Link to the converter's repository](https://github.com/MateuszBurak/currency-converter-input)

This converter converts currency values from PLN to EUR, USD and GBP. It follows BEM convention.

## How to use

To use it, simply input the amount and choose the currency you want the outcome to be in.

## Code

Since this simple converter does not use api, as it's mostly meant to practice the *input* element, it uses convertion data from early 2023.

It uses ES6+ features.

It's code consists of 3 functions:

```javascript
    const calculate = (amount, currency, signElement) => {

        const currencyEUR = 4.63;
        const currencyUSD = 4.16;
        const currencyGBP = 5.23;

        switch (currency) {
            case "EUR":
                signElement.innerText = " €";
                return amount / currencyEUR;
            case "USD":
                signElement.innerText = " $";
                return amount / currencyUSD;
            case "GBP":
                signElement.innerText = " £";
                return amount / currencyGBP;
        }
    }
```
```javascript
const calculateResult = () => {

        const amountElement = document.querySelector(".js-amount");
        const currencyElement = document.querySelector(".js-currency");
        const signElement = document.querySelector(".js-sign");

        const result = calculate(+amountElement.value, currencyElement.value, signElement);

        const resultElement = document.querySelector(".js-result");

        resultElement.innerText = result.toFixed(2);
    }
```

```javascript
    const init = () => {

        const formElement = document.querySelector(".js-form");

        formElement.addEventListener("input", calculateResult)
    }
    init();
```
