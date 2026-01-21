# Simple Assertions Plugin

The **Simple Assertions** plugin provides an easy and intuitive way to validate HTTP responses directly inside Voiden. It allows you to verify not only response bodies, but also **status**, **status codes**, **headers**, and **response time**, all from a clean, table-based interface integrated into the response panel.

This makes assertion testing lightweight, readable, and tightly coupled with real API responses—without adding unnecessary complexity.

---

## What You Can Assert

The Simple Assertions plugin now supports assertions on multiple parts of an HTTP response:

- **Status** (success or failure state)
- **Status Code** (e.g. 200, 201, 400, 500)
- **Response Time** (performance checks)
- **Headers** (specific header values)
- **Body** (JSON, XML, or form data)

This gives you both **functional validation** and **basic performance checks** in one place.

---

## Key Features

### **Assertion Table Interface**

- Clean, easy-to-read table format:

  | Description | Field | Key | Expexted Value |
  | --- | --- | --- | --- |
 

- Insertable using the `/assertions` slash command

![assertion](/img/plugins/openapi-collection/simple-assertion.gif)

The table format keeps tests readable, even when you add multiple assertions.

---

### **Supported Assertion Targets**

You can create assertions against:

- **Response Status**
  - Example: **status and statusCode**
   
   | Description | Field | Key | Expexted Value |
  | --- | --- | --- | --- |
  | Check Status | `status` or `statusCode` | greater-than | 200 |

- **Status Text**

 | Description | Field | Key | Expexted Value |
  | --- | --- | --- | --- |
  | Check Status Text | `statusText` | equals | OK |

- **Response Time**

 | Description | Field | Key | Expexted Value |
  | --- | --- | --- | --- |
  | Check Response Time | `responseTime` or `duration` | less-than | 500 |

- **Response Headers**

| Description | Field | Key | Expexted Value |
  | --- | --- | --- | --- |
  | Check Header Connection | `header.connection` | equals | close |

- **Response Body**

| Description | Field | Key | Expexted Value |
  | --- | --- | --- | --- |
  | Check Response Body | `body.method` | contains | POST |

  - JSON (via JSONPath)
  - XML (via XPath)
  - Form fields

---

### **Supported Operators**

The following operators are available across supported fields:

- `equals`
- `not equals`
- `contains`
- `exists`
- `matches`
- `starts with`
- `ends with`

These operators allow both strict checks and flexible pattern-based validation.

---

## Result Visualization

- Assertion results appear as a **sub-panel** inside the response tab
- Each assertion is evaluated independently
- Clear, color-coded feedback:
  - **Pass** — Green
  - **Fail** — Red

This makes it easy to immediately understand what worked and what didn’t—without digging through logs.

---

## Why Use Simple Assertions

- Validate API behavior without writing scripts
- Catch incorrect responses early
- Verify performance with response time checks
- Ensure headers and status codes are correct
- Keep tests close to real responses

Simple Assertions are designed to be quick, visual, and easy to maintain—ideal for both exploratory testing and everyday API validation.

---

## Summary

The Simple Assertions plugin in Voiden lets you validate **status**, **status codes**, **response time**, **response headers**, and **response bodies** using a simple table-based interface. With clear operators and visual feedback built directly into the response panel, it provides a practical and approachable way to add confidence to your API testing workflow.
