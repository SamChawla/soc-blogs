---
title: "Day 1. Prerequisites and Best Practices"
seoTitle: "Django Pre requisites"
datePublished: Fri Sep 20 2024 16:04:41 GMT+0000 (Coordinated Universal Time)
cuid: cm1awvpkj001u09ie1ypv0tlr
slug: day-1-prerequisites-and-best-practices
tags: python, django, python-beginner, slice-of-code

---

Starting a new Django project is an exciting venture into web development with Python. However, setting up your development environment correctly is crucial for a smooth and efficient workflow. This guide will walk you through the essential prerequisites for creating a Django project, ensuring you're well-prepared to dive into coding.

## Python Installation

Before you can start working with Django, you need to have Python installed on your system.

### Step 1: Download Python

* **Visit the Python website:** Go to [https://www.python.org](https://www.python.org/downloads/)/.
    
* **Download the latest version or the version you need to work on:** The website will automatically suggest the latest version suitable for your operating system (Windows or macOS). You can click on `view full list of downloads` to check other versions as well.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1726845380368/7753339f-825b-476a-bcfd-b7e0a0231634.png align="center")
    

### Step 2: Install Python on Windows

1. **Run the installer:** Double-click the downloaded `.exe` file.
    
2. **Add Python to PATH:** **Important!** Check the box that says **"Add Python to PATH"**. This allows you to run Python from the command line.
    
3. **Choose installation type:**
    
    * **Install Now:** For a standard installation.
        
    * **Customize Installation:** If you need specific features.
        
4. **Complete the installation:** Click **Install** and wait for the process to finish.
    
5. **Verify the installation:** Open **Command Prompt** and run:
    
    ```bash
    python --version # or python3 --version
    ```
    
    You should see the installed Python version.
    

### Step 3: Install Python on macOS

1. **Run the installer:** Open the downloaded `.pkg` file.
    
2. **Follow the prompts:** Proceed through the installation steps.
    
3. **Verify the installation:** Open **Terminal** and run:
    
    ```bash
    python3 --version
    ```
    
    Note: macOS may come with Python 2 pre-installed. Use `python3` to access the latest version.
    

## Handling Permission Issues in Python

Sometimes, you might encounter permission issues when running Python scripts or activating virtual environments, especially on Windows.

### Setting Execution Policy in PowerShell

**Issue:** When activating a virtual environment in PowerShell, you might see an error like:

```bash
File cannot be loaded because running scripts is disabled on this system.
```

**Solution:**

1. **Open PowerShell as Administrator:**
    
    * Right-click on PowerShell and select **"Run as administrator"**.
        
2. **Set Execution Policy:**
    
    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
    ```
    
    * This command allows you to run local scripts that you've created yourself.
        
3. **Activate the virtual environment again:**
    
    ```powershell
    .\venv\Scripts\Activate
    ```
    
    ### Turning Off Execution Aliases from Microsoft Store (Issue Fix)
    
    **Issue:** Typing `python` in Command Prompt opens the Microsoft Store instead of running Python.
    
    **Solution:**
    
    1. **Open Windows Settings:** Press **Win + I**.
        
    2. **Navigate to Apps:** Go to **Apps &gt; Apps & Features**.
        
    3. **Manage App Execution Aliases:**
        
        * Click on **"App execution aliases"**.
            
    4. **Disable Python Aliases:**
        
        * Find **"Python"** and **"Python3"** in the list and toggle them **Off**.
            
    
    **Verify Python Command:**
    
    * Open **Command Prompt** or **PowerShell** and run:
        
        ```powershell
        python --version
        ```
        
        It should display the Python version, not open the Microsoft Store.
        

## Virtual Environments: `venv` and Alternatives

Virtual environments are essential for managing dependencies and isolating project-specific packages.

### What is `venv`?

* `venv`: A built-in Python module that creates isolated environments.
    
* **Purpose:** Keeps dependencies required by different projects separate.
    
* **Benefits:**
    
    * Avoids version conflicts.
        
    * Keeps your global Python installation clean.
        

### Alternatives to `venv`

#### `virtualenv`

* **Overview:** A third-party tool that offers more features than `venv`.
    
* **Advantages:**
    
    * Works with older Python versions (&lt;3.3).
        
    * Can create environments with different Python interpreters.
        
* **Usage:** Install using `pip install virtualenv`.
    

#### `conda`

* **Overview:** An environment and package manager that supports multiple languages.
    
* **Advantages:**
    
    * Manages system-level dependencies.
        
    * Ideal for data science projects.
        
* **Usage:** Comes with Anaconda or Miniconda distributions.
    

#### `pipenv`

* **Overview:** Combines `pip` and `virtualenv` into a single tool.
    
* **Features:**
    
    * Automates virtual environment creation.
        
    * Uses `Pipfile` and `Pipfile.lock` for dependency management.
        
* **Usage:** Install using `pip install pipenv`.
    

### Choosing the Right Tool

* **Use** `venv` for straightforward projects where basic environment isolation is sufficient.
    
* **Use** `virtualenv` if you need compatibility with older Python versions.
    
* **Use** `conda` for projects requiring packages beyond Python or complex dependencies.
    
* **Use** `pipenv` for enhanced dependency management and when you prefer an integrated approach.
    

## Setting Up `venv` for a Django Project

### Step 1: Create a Virtual Environment

1. **Open Command Prompt or Terminal.**
    
2. **Navigate to your project directory:**
    
    ```powershell
    cd path/to/your/project
    ```
    
3. **Create the virtual environment:**
    
    ```powershell
    python -m venv venv
    ```
    
    * This command creates a folder named `venv` with the isolated Python environment. You can change last `venv` to provide a meaningful name.
        
    * e.g `python -m venv pp_venv`
        

### Step 2: Activate the Virtual Environment

**On Windows:**

* **Command Prompt:**
    
    ```powershell
    venv\Scripts\activate
    ```
    
* **PowerShell:**
    
    ```powershell
    .\venv\Scripts\Activate
    ```
    

**On macOS/Linux:**

```powershell
source venv/bin/activate
```

* After activation, your prompt will prefix with `(venv)` indicating the environment is active.
    

### Step 3: Verify the Virtual Environment

* **Check Python Path:**
    
    ```powershell
    which python
    ```
    
    * Should point to the Python executable inside your `venv` directory.
        
* **Check Installed Packages:**
    
    ```powershell
    pip list
    ```
    
    * Should show a minimal list of packages.
        

## Formatting and Linting Tools

Maintaining code quality is crucial. Formatting and linting tools help enforce coding standards and catch potential issues early.

### 1\. Black (Code Formatter)

* **Description:** An uncompromising Python code formatter.
    
* **Installation:**
    
    ```powershell
    pip install black
    ```
    
* **Usage:**
    
    * Format a single file:
        
        ```powershell
        black filename.py
        ```
        
    * Format all files in a directory:
        
        ```powershell
        black .
        ```
        
* **Integration with VS Code:**
    
    * Install the **"Python"** extension.
        
    * Set Black as the default formatter in settings.
        

### 2\. isort (Import Sorting)

* **Description:** Automatically sorts imports in your Python files.
    
* **Installation:**
    
    ```powershell
    pip install isort
    ```
    
* **Usage:**
    
    * Sort imports in a file:
        
        ```powershell
        isort filename.py
        ```
        
    * Sort imports in all files:
        
        ```powershell
        isort .
        ```
        
* **Integration with Black:**
    
    * Can be used together to format code and organize imports.
        

### 3\. pylint (Code Linter)

* **Description:** A static code analyzer to find programming errors and enforce a coding standard.
    
* **Installation:**
    
    ```powershell
    pip install pylint
    ```
    
* **Usage:**
    
    ```powershell
    pylint filename.py
    ```
    
* **Customization:**
    
    * Create a `.pylintrc` file to customize rules.
        

### 4\. ruff (Fast Linter and Formatter)

* **Description:** A fast Python linter and formatter combining functionalities of multiple tools.
    
* **Installation:**
    
    ```powershell
    pip install ruff
    ```
    
* **Usage:**
    
    ```powershell
    ruff check .
    ```
    
* **Advantages:**
    
    * High performance.
        
    * Supports a wide range of linting rules.
        

## VS Code Extensions for Django Development

Visual Studio Code is a powerful editor with a rich ecosystem of extensions that enhance Django development.

### 1\. Python Extension

* **Publisher:** Microsoft
    
* **Features:**
    
    * IntelliSense (autocompletion)
        
    * Linting and code analysis
        
    * Debugging support
        
    * Code navigation and refactoring
        
* **Installation:**
    
    * Open VS Code.
        
    * Go to the Extensions view (`Ctrl+Shift+X`).
        
    * Search for **"Python"** and install.
        

### 2\. Djanesia

* **Features:**
    
    * Django snippets for models, views, forms, and templates.
        
    * Improved syntax highlighting for Django code.
        
* **Installation:**
    
    * Search for **"Djanesia"** in the Extensions view and install.
        

### 3\. Symbols

* **Features:**
    
    * A simple file icon theme for VS Code
        
    * Enhances visual navigation within the project.
        
* **Installation:**
    
    * Search for **"Symbols"** in the Extensions view and install.
        

### 4\. Additional Useful Extensions

* **GitLens:** Supercharges Git capabilities within VS Code.
    
* **Prettier - Code Formatter:** Can format code according to specified rules.
    
* **Bracket Pair Colorizer:** Makes it easier to identify matching brackets.
    
* **ESLint:** If you're working with JavaScript in your Django templates.
    

## Git Basics

Version control is essential for tracking changes and collaborating with others.

### Why Use Git?

* **Track Changes:** Keep a history of modifications.
    
* **Collaboration:** Work with others without conflicts.
    
* **Branching:** Experiment with new features safely.
    

### Basic Git Commands

* **Initialize a repository:**
    
    ```powershell
    git init
    ```
    
* **Clone a repository:**
    
    ```powershell
    git clone <repository-url>
    ```
    
* **Check status:**
    
    ```powershell
    git status
    ```
    
* **Add changes:**
    
    ```powershell
    git add <file>
    ```
    
* **Commit changes:**
    
    ```powershell
    git commit -m "Commit message"
    ```
    
* **Push to remote repository:**
    
    ```powershell
    git push origin main
    ```
    
* **Pull updates:**
    
    ```powershell
    git pull
    ```
    
    More Info on Git can be found [here](https://simplykeep.in/getting-started-with-github).
    

### Best Practices

* **Commit Often:** Keep commits small and focused. For writing meaningful commit messages follow [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/).
    
* **Write Meaningful Commit Messages:** Describe what changes you made and why.
    
* **Use Branches:** For new features or bug fixes, create separate branches.
    

### Git Integration with VS Code

* **Built-in Git Support:** VS Code has Git integration out of the box.
    
* **Source Control Panel:** Accessed via the left sidebar, allows staging, committing, and pushing changes.
    
* **GitLens Extension:** Provides advanced Git features like code authorship and history.
    

---

## Database Setup

Django supports various databases; PostgreSQL is a popular choice for its robustness and features.

### PostgreSQL

#### Description

* **Overview:** An open-source relational database management system.
    
* **Features:** Advanced SQL support, extensibility, and data integrity.
    

#### Installation

1. **Download Installer:**
    
    * Visit the [official PostgreSQL website](https://www.postgresql.org/download/).
        
2. **Run Installer:**
    
    * Follow the installation wizard.
        
    * Set a password for the `postgres` user.
        
3. **Verify Installation:**
    
    * Open Command Prompt or Terminal and run:
        
        ```powershell
        psql --version
        ```
        

### DBViewer (Optional)

* **Purpose:** A graphical tool to manage and interact with your database.
    
* **Alternatives:** pgAdmin, DBeaver, or TablePlus.
    
* **Features:**
    
    * Visualize database schemas.
        
    * Execute SQL queries.
        
    * Manage data and structures.
        

---

## Conclusion

Setting up the prerequisites for a Django project may seem daunting, but each step is crucial for a smooth development experience. By ensuring Python is correctly installed, handling permission issues, using virtual environments, setting up code formatting and linting tools, enhancing your editor with extensions, understanding Git basics, and configuring your database, you're well on your way to building robust Django applications.

**Additional Resources:**

* [Official Django Documentation](https://docs.djangoproject.com/)
    
* [VS Code Python Extension Documentation](https://code.visualstudio.com/docs/languages/python)
    
* [Git Documentation](https://git-scm.com/doc)
    
* [PostgreSQL Documentation](https://www.postgresql.org/docs/)