#  Maestro Android UI Automation (MyDemoApp)

This repository contains automated UI tests for **MyDemoApp Android application** using **Maestro**.

The project demonstrates both:

 **Local testing using a real Android device (via ADB over USB)**
 **CI/CD automation using GitHub Actions with an Android Emulator**

---

## Project Overview

Initially, all test cases were created and executed **locally** using a **real Android device connected via USB (ADB)**.
After verifying the tests, they were pushed to GitHub and integrated with **CI/CD** using GitHub Actions.

This allows anyone to:

* Run tests locally on a real device
* Run tests automatically in the cloud (without a physical device)

---

##  Project Structure

```
.
├── .github/workflows/maestro.yml     # CI/CD workflow
├── app/
│   └── mydemoapp.apk                # Android APK
├── myappdemo/
│   └── maestro_scripts/
│       ├── login.yaml
│       ├── draw.yaml
│       ├── Sorting.yaml
```

---

## Tools & Technologies

* Maestro (UI automation)
* ADB (Android Debug Bridge)
* Android Emulator (CI)
* GitHub Actions (CI/CD)
* Java 17

---

##  Local Testing (Real Device via ADB)

### Step 1: Connect Device

* Connect your Android phone via USB
* Enable **USB Debugging**

Check connection:

```bash
adb devices
```

---

### Step 2: Install APK

```bash
adb install app/mydemoapp.apk
```

---

### Step 3: Run Maestro Tests

```bash
maestro test myappdemo/maestro_scripts
```

This runs all test scripts on your real device

---

##  CI/CD Testing (GitHub Actions)

This project includes a workflow file:

```
.github/workflows/maestro.yml
```

### What happens in CI?

When you push code to GitHub:

1.  Ubuntu runner starts
2.  Java 17 is installed
3.  Maestro is installed
4.  Android Emulator is created and launched
5.  APK is installed in emulator
6.  Maestro tests are executed
7.  Test report is generated

---

##  How Others Can Use This Repo

### Option 1: Run Locally (Recommended)

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo

adb devices
adb install app/mydemoapp.apk

maestro test myappdemo/maestro_scripts
```

---



This project shows a complete workflow of:

* Testing on a real device using ADB
* Automating tests using Maestro
* Integrating CI/CD using GitHub Actions

It can be easily reused by anyone to perform Android UI automation both locally and in the cloud.

---
