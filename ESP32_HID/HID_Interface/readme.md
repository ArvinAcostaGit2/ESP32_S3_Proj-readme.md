# Q&A / Alias Manager – Full Process Flow & Features Analysis

> **File:** `alias-manager.html`  
> **Author:** ChatGPT (original implementation)  
> **Date:** 2025-10-28  

---

## Overview

`alias-manager.html` is a **single-file, client-side web app** that lets users store **key/value alias pairs** (e.g., `prod_server_ip → 10.10.10.1:22`) in the browser using **IndexedDB**.  
It supports **multiple named databases**, full **CRUD** operations, and a polished UI – all without any server or external libraries.

---

## 1. Page Load & Initialization

```html
<body onload="init()">


Action,Trigger,Result
Select,“Use Selected Database”,currentSelectedDB set → handleDbSelected() → UI updates
Create,“Add New Database” → enter name → “Create and Use Database”,"New IndexedDB created with object store qa_items (auto-increment id, index queIndex)"
Delete,“Remove Selected Database” + confirmation,Entire DB removed via indexedDB.deleteDatabase()
