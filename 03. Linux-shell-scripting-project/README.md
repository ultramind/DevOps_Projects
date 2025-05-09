# LINUX SHELL SCRIPTING CAPSTONE PROJECT

##  Table of Contents

1. [Project Overview](#project-overview)
2. [Project Steps and Commands](#project-steps-and-commands)
   - [2.1 Create Project Directory](#21-create-project-directory)
   - [2.2 Initialize Git Repository](#22-initialize-git-repository)
   - [2.3 Create the Bash Script File (.sh)](#23-create-the-bash-script-file-sh)
   - [2.4 Make the Script Executable](#24-make-the-script-executable)
3. [Script Implementation Steps](#script-implementation-steps)
   - [3.1 Prompt for User Input](#31-prompt-for-user-input)
   - [3.2 Ask for Table Type (Full or Partial)](#32-ask-for-table-type-full-or-partial)
   - [3.3 Full Multiplication Table](#33-full-multiplication-table)
   - [3.4 Partial Multiplication Table](#34-partial-multiplication-table)
   - [3.5 Validate Input Range for Partial Table](#35-validate-input-range-for-partial-table)
   - [3.6 Handle Invalid Options](#36-handle-invalid-options)
4. [Troubleshooting (Common Issues and Solutions)](#troubleshooting-common-issues-and-solutions)

---

## 📌 Project Overview

This capstone project demonstrates Linux shell scripting skills by creating a dynamic **Multiplication Table Generator** using **Bash scripting**. The project follows structured development with **Git for version control** and showcases best practices in shell scripting, input validation, and troubleshooting.

---

## 📌 Project Steps and Commands

### 2.1 Create Project Directory
```sh
mkdir linux_shell_project && cd linux_shell_project
```
![Project Directory](https://github.com/user-attachments/assets/2471c150-e12e-4c94-87f7-af943e0320a6)

### 2.2 Initialize Git Repository
```sh
git init
```
![Git Init](https://github.com/user-attachments/assets/03de63e3-3bdb-400b-bb48-8b5b6c323182)

### 2.3 Create the Bash Script File (.sh)
```sh
touch multiplication_table.sh
nano multiplication_table.sh
```
![Create Script](https://github.com/user-attachments/assets/ff532589-712d-42e3-a0fa-69190ad133f6)

**Enter the following Bash code:**

```
```
![Enter Code](https://github.com/user-attachments/assets/79b0d3d2-5632-43af-b0ec-07e7373adfc7)

### 2.4 Make the Script Executable
```sh
chmod +x multiplication_table.sh
```
![Make Executable](https://github.com/user-attachments/assets/b7f48060-2040-45b3-bec9-09ec99d43e26)

---

## 📌 Script Implementation Steps

### 3.1 Prompt for User Input
```sh
echo "Enter a number: "
read number
```
![User Input](https://github.com/user-attachments/assets/b033e9cf-facb-400b-b21a-11d9cea2094a)

### 3.2 Ask for Table Type (Full or Partial)
```sh
echo "Choose: (1) Full Table (2) Partial Table"
read choice
```
![Table Choice](https://github.com/user-attachments/assets/05a87cd3-530a-495a-a0ab-21b95861b825)

### 3.3 Full Multiplication Table
```sh
for i in {1..10}
do
echo "$number x $i = $(($number * $i))"
done
```
![Full Table](https://github.com/user-attachments/assets/1d712192-99b5-434a-86de-f4f39ea18a66)

### 3.4 Partial Multiplication Table
```sh
echo "Enter start range:"
read start
echo "Enter end range:"
read end
for i in $(seq $start $end)
do
echo "$number x $i = $(($number * $i))"
done
```
![Partial Table](https://github.com/user-attachments/assets/7bed7ca8-a9ed-4433-b4b0-98ec559cbabc)

### 3.5 Validate Input Range for Partial Table
```sh
if [[ $start -gt $end ]]; then
echo "Invalid range! Start must be less than or equal to End."
exit 1
fi
```
![Input Validation](https://github.com/user-attachments/assets/b6eed785-4055-4600-b214-41952aa5c3e9)

### 3.6 Handle Invalid Options
```sh
if [[ $choice -ne 1 && $choice -ne 2 ]]; then
echo "Invalid choice. Please enter 1 or 2."
exit 1
fi
```
![Invalid Options](https://github.com/user-attachments/assets/421ce0cf-7e71-4acc-959a-26f203fcd0b7)

---

## 📌 Troubleshooting (Common Issues and Solutions)

### ❗ 4.1 Script Permission Denied
**Issue:** "Permission Denied" when running the script.

✅ **Solution:**
```sh
chmod +x multiplication_table.sh
```

### ❗ 4.2 Invalid Input for Number
**Issue:** Non-numeric values break the script.

✅ **Solution:** Add input validation:
```sh
if ! [[ "$number" =~ ^[0-9]+$ ]]; then
echo "Invalid input. Enter a number."
exit 1
fi
```

### ❗ 4.3 Git Remote Connection Issues
**Issue:** Unable to push code to GitHub.

✅ **Solution:**
```sh
git remote -v
git remote add origin <repository_url>
git push -u origin main
```

---

## 🎯 Conclusion

This capstone project demonstrates proficiency in **Linux shell scripting**, **Git version control**, and **troubleshooting Bash scripts**. By implementing structured Bash scripts with input validation and error handling, the project highlights best practices in automation and scripting for DevOps.

**🚀 Next Steps:** Enhance the script with logging, error tracking, and automation features.

---

