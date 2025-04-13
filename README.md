
# react-flex-filters

A customizable and user-friendly React search/filter component that allows users to dynamically filter data using various input types like text, dropdown, and boolean switches. Designed to be simple to integrate and flexible to configure.

---

## ✨ Features

- Supports multiple filter types: **text**, **dropdown**, and **boolean**
- Allows **single** or **multiple filters** to be applied
- Dynamic **dropdown rendering** based on selected filter type
- Filter **removal** and **update** support
- Easy to customize with colors, width, and styles

---

## 📦 Installation

```bash
npm install react-flex-filters
```

or

```bash
yarn add react-flex-filters
```

---

## 🚀 Usage

```jsx
import React from "react";
import { FlexFilters } from "react-flex-filters";

const data = [
  {
    type: "text",
    label: "Name",
    description: "Filter by entering a specific name (e.g., first or last name).",
    key: "name",
  },
  {
    type: "dropdown",
    label: "Gender",
    description: "Filter by selecting a gender from predefined options (e.g., Male, Female).",
    key: "gender",
    options: ["Male", "Female"],
  },
  {
    type: "boolean",
    label: "Is Eligible",
    description: "Filter by eligibility status (e.g., Yes or No).",
    key: "is_eligible",
  },
  {
    type: "text",
    label: "Email ID",
    description: "Filter by entering a specific email address.",
    key: "email_id",
  },
  {
    type: "dropdown",
    label: "Education",
    description: "Filter by selecting an education level (e.g., High School, Bachelor's, Master's).",
    key: "education",
    options: ["High School", "Bachelor's", "Master's"],
  },
];

function App() {
  const handleFilter = (filteredData) => {
    console.log("Filtered values:", filteredData);
  };

  return (
    <FlexFilters
      data={data}
      onFilter={handleFilter}
    />
  );
}
```

---

## 🛠 Props

| Prop               | Type       | Required | Description                                                                 |
|--------------------|------------|----------|-----------------------------------------------------------------------------|
| `data`             | `Array`    | ✅       | Array of filter config objects (see example above)                         |
| `width`            | `string`   | ❌       | Width of the search box container (e.g., `"300px"`, `"100%"`)             |
| `primaryColor`     | `string`   | ❌       | Primary color (e.g., for selected filter chips)                            |
| `secondaryColor`   | `string`   | ❌       | Background color for inputs/dropdowns                                      |
| `removeButtonColor`| `string`   | ❌       | Color for the remove filter button                                         |
| `placeholderText`  | `string`   | ❌       | Placeholder text for the main input                                        |
| `onFilter`         | `function` | ✅       | Callback function called when filters are added or removed                 |
| `className`        | `string`   | ❌       | Custom class name(s) for the root container                                |

---

## 📌 Filter Data Format

Each object in the `data` array should follow this structure:

```js
{
  type: "text" | "dropdown" | "boolean",
  label: "Label shown in dropdown",
  description: "Helper text shown optionally",
  key: "unique_key_for_filter",
  options: ["Option1", "Option2"] // required only for dropdown type
}
```

---

## 🧪 Example

```js
const data = [
  { type: "text", label: "Name", key: "name" },
  { type: "dropdown", label: "Gender", key: "gender", options: ["Male", "Female"] },
  { type: "boolean", label: "Is Eligible", key: "is_eligible" }
];
```

---

## 📤 Output

The `onFilter` callback returns an object with active filter key-value pairs, e.g.:

```js
{
  name: "John",
  gender: "Male",
  is_eligible: true
}
```

---

## 📄 License

MIT
