## SOP: JQ Intro Documentation

<div align="center">
  <img src="https://static.vecteezy.com/system/resources/previews/016/836/010/non_2x/jq-letter-logo-with-colorful-rainbow-texture-pro-vector.jpg" alt="JQ Logo" width="40%"/>
</div>










| Created     | Version | Author         | Comment          | Reviewer |
|-------------|---------|----------------|------------------|----------|
| 18-04-2025  | V1      | Vardaan Saxena | Internal Review  | Pritam   |

---

## Table of Contents

1. [Intro](#intro)  
2. [Why JQ?](#why-jq)  
3. [What is JQ?](#what-is-jq)  
4. [Key Features](#key-features)  
5. [Installation](#installation)  
6. [Basic Usage](#basic-usage)  
7. [Common JQ Filters](#common-jq-filters)  
8. [Working with Arrays](#working-with-arrays)  
9. [Parsing Nested JSON](#parsing-nested-json)  
10. [Real-World Examples](#real-world-examples)  
11. [Troubleshooting](#troubleshooting)  
12. [References](#references)  
13. [Contact](#contact)  


---

##  Intro <a id="intro"></a>

This SOP provides an **introductory guide** to using **JQ**, a lightweight and flexible command-line JSON processor.

---

##  Why JQ? <a id="why-jq"></a>

- 🔹 Efficiently parse, filter, and transform JSON data  
- 🔹 Ideal for DevOps, scripting, and data manipulation  
- 🔹 Works well with shell tools like `curl`, `grep`, `awk`, etc.  
- 🔹 No need for full-fledged programming to handle JSON  

---

##  What is JQ? <a id="what-is-jq"></a>

**JQ** is a powerful command-line tool that allows you to parse, transform, filter, and manipulate JSON data quickly and easily. Think of it as `sed` or `awk`, but specifically designed for JSON.

---

##  Key Features <a id="key-features"></a>

- ✅ JSON parsing & querying  
- ✅ Filtering and transformation  
- ✅ Supports complex data extraction  
- ✅ Can format JSON (pretty/compact)  
- ✅ Lightweight and fast  
- ✅ Can work in pipelines  

---

##  Installation <a id="installation"></a>

### 🔧 For Ubuntu/Debian:

```bash
sudo apt update
sudo apt install jq -y
```

### 🔧 For macOS (using Homebrew):

```bash
brew install jq
```

### 🔧 For Windows:

- Download the `.exe` file from [https://stedolan.github.io/jq/download/](https://stedolan.github.io/jq/download/)
- Add it to your system path for CLI access.

---

##  Basic Usage <a id="basic-usage"></a>

Pretty-print a JSON file:

```bash
cat data.json | jq .
```

Get a specific key:

```bash
cat data.json | jq '.name'
```

---

##  Common JQ Filters <a id="common-jq-filters"></a>

- `.` → the entire input  
- `.key` → access a key  
- `[]` → iterate over arrays  
- `|` → chain operations  
- `map()` → transform each item  
- `select()` → filter based on condition

---

##  Working with Arrays <a id="working-with-arrays"></a>

### 🔹 Example JSON:
```json
[
  { "name": "Alice", "age": 25 },
  { "name": "Bob", "age": 30 }
]
```

### 🔹 Extract names:

```bash
jq '.[].name' data.json
```

### 🔹 Filter by age:

```bash
jq '.[] | select(.age > 26)' data.json
```

---

##  Parsing Nested JSON <a id="parsing-nested-json"></a>

### 🔹 Sample JSON:
```json
{
  "user": {
    "id": 1,
    "profile": {
      "name": "Alice",
      "email": "alice@example.com"
    }
  }
}
```

### 🔹 Get email:

```bash
jq '.user.profile.email' data.json
```

---

##  Real-World Examples <a id="real-world-examples"></a>

### ✅ Fetch API data and extract field:

```bash
curl -s https://api.example.com/users | jq '.[].username'
```

### ✅ Format JSON in compact form:

```bash
jq -c . data.json
```

### ✅ Save filtered output:

```bash
jq '.users[] | select(.active == true)' data.json > active_users.json
```

---

##  Troubleshooting <a id="troubleshooting"></a>

- ❌ **Invalid JSON Input** — Ensure your input file has proper JSON format  
- ❌ **Null Output** — Check if the key exists or the filter is correctly written  
- ❌ **Permission Denied** — Verify file permissions if reading from a file  

---

##  References <a id="references"></a>

- 🌐 [JQ Official Docs](https://stedolan.github.io/jq/manual/)
- 🌐 [JQ Tutorial by TutorialsPoint](https://www.tutorialspoint.com/jq/index.htm)
- 🌐 [JQ Playground](https://jqplay.org)

---

##  Contacts <a id="contacts"></a>

| 👤 Name           | 📧 Email Address                                |
|------------------|--------------------------------------------------|
| Vardaan Saxena   | vardaan.saxena.snaatak@mygurukulam.co           |

---

##  Conclusion <a id="conclusion"></a>

JQ is a versatile and powerful tool to deal with JSON data on the command line. From formatting to advanced filtering and data transformation, it simplifies tasks that would otherwise require writing scripts. Mastering JQ will significantly improve your productivity in data handling and automation tasks.

---
