# Currency Conversion Calculator | JavaScript & jQuery

## Overview

This project is an interactive currency conversion calculator built using JavaScript, jQuery, HTML, and JSON. The application allows users to convert US dollars (USD) into different currencies using exchange rate data provided in JSON format.

The goal was to strengthen my understanding of event-driven programming, DOM manipulation, JSON parsing, and dynamic user interface updates by creating a responsive currency conversion tool.

## Technologies Used

- **HTML** — Application structure and input elements
- **JavaScript** — Currency conversion logic
- **jQuery** — DOM manipulation and event handling
- **JSON** — Exchange rate data storage and parsing
- **OpenExchangeRates.org** — Source of sample exchange rate data

## Features

| Feature | Description |
|---|---|
| Currency Selection | Dynamically generates dropdown options based on available exchange rates. |
| Currency Conversion | Converts user-entered USD amounts into the selected currency. |
| Dynamic Labels | Updates the output label to display the selected currency's name and abbreviation. |
| JSON Rate Updates | Allows users to replace exchange rate data using a JSON-formatted string. |
| Automatic Calculations | Performs conversions immediately after a currency is selected. |
| Result Formatting | Displays converted amounts rounded to two decimal places. |
| Form Reset | Resets the conversion result and label when exchange rates are updated. |

## How It Works

### 1. Dynamic Currency Dropdown

When the page loads, a jQuery `ready` event handler populates the currency dropdown using the available exchange rates.

Each option displays the currency's full name and abbreviation.

Example:

```text
Select currency
Bitcoin (BTC)
Canadian Dollar (CAD)
Euro (EUR)
Japanese Yen (JPY)
United States Dollar (USD)
```

Only currencies included in the current exchange rate data appear in the dropdown.

### 2. Currency Conversion

When a user selects a currency, a jQuery `change` event handler retrieves the corresponding exchange rate and converts the entered USD amount.

The calculation follows:

**Converted Amount = USD Amount × Exchange Rate**

For example:

```text
USD Amount: 100.00
Selected Currency: Canadian Dollar (CAD)
Exchange Rate: 1.316853

Converted Amount: 131.69 CAD
```

The converted amount is displayed in a read-only input field with two decimal places.

### 3. Updating Exchange Rates

Users can modify the available exchange rates by entering JSON data into a text area and clicking the **Update Rates** button.

A jQuery `click` event handler:

1. Retrieves the JSON-formatted exchange rate data.
2. Parses the JSON using `JSON.parse()`.
3. Updates the application's exchange rate object.
4. Rebuilds the currency dropdown based on the new rates.
5. Resets the conversion result and currency label.

Example exchange rate data:

```json
{
  "rates": {
    "CAD": 1.316853,
    "EUR": 0.92,
    "JPY": 149.50,
    "USD": 1
  }
}
```

These rates are illustrative sample values.

## Implementation Approach

### jQuery Event Handling

The application uses three event handlers to manage interactions:

- **`ready()`** — Initializes the available currency options when the page loads.
- **`change()`** — Performs currency conversions when the selected currency changes.
- **`click()`** — Updates exchange rate information when the user requests new rates.

### DOM Manipulation

jQuery dynamically updates the user interface by modifying dropdown options, input values, and labels without requiring a page reload.

### JSON Parsing

Exchange rate data is stored in JSON format and converted into a JavaScript object using `JSON.parse()`.

This allows the calculator to adapt to different sets of currencies without hardcoding the available options.

## Testing & Validation

The application is designed to handle the following scenarios:

- Displaying only currencies included in the exchange rate data
- Generating correctly formatted currency names and abbreviations
- Converting USD amounts using the selected exchange rate
- Formatting conversion results to two decimal places
- Updating the conversion result when a different currency is selected
- Rebuilding the currency dropdown after loading new JSON data
- Resetting the output field and label after exchange rate updates

## Key Learning Outcomes

Through this project, I strengthened my understanding of:

- **Event-Driven Programming:** Responding to user interactions through jQuery event handlers.
- **DOM Manipulation:** Dynamically updating HTML elements and their content.
- **JSON Data Processing:** Parsing and accessing structured exchange rate information.
- **Dynamic UI Development:** Creating interface elements based on available data.
- **JavaScript Calculations:** Performing currency conversions and formatting numerical results.
- **User Interface Design:** Providing immediate feedback through interactive form elements.

## Project Context

Developed as part of a JavaScript and jQuery programming lab, this project focused on applying client-side web development techniques to build an interactive, data-driven calculator.

The project demonstrates how JavaScript, jQuery, and JSON can work together to create responsive web applications that adapt to user input and changing data.
