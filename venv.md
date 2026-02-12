
# Virtual Environment

## What is virtual environment?

- A **virtual environment** is an isolated space for a specific project.
- Its packages and dependencies are installed independently from other projects.
  
## Why do we need a virtual environment?

- Avoid version conflicts
- Keep system packages safe
- Easy to share projects

## What are environment variables?

- These are variables stored in your operating system that contain information such as where to find files, which user is logged in, and which shell is running.

```bash 
$PATH $HOME $PWD 
````

## printenv

* It shows all environment variables stored in the current shell session

## Lifecycle of Virtual Environment

### 1. Create a Virtual Environment

```bash
python3 -m venv venv
```

* This creates a folder named `venv` containing the virtual environment.

### 2. Activate the Virtual Environment

On Linux / macOS:

```bash
source venv/bin/activate
```

or

```bash
. venv/bin/activate
```

#### Activate

* It modifies `PATH` and adds the virtual environment's `bin` directory to the front of **PATH**.

  Before activation:

  ```bash
  which python

  /usr/bin/python
  ```

  After activation:

  ```bash
  which python 
  
  /home/user/project/venv/bin/python
  ```

* Sets environment variables like `VIRTUAL_ENV`:

  ```bash
  printenv VIRTUAL_ENV
  /home/user/project/venv
  ```

* Changes the shell prompt, showing `(venv)` at the start of the prompt.

#### Source

* This command runs the **activate** script in the current shell session, not in a temporary child shell.
* It ensures the above changes happen in the current shell session.

### 3. Verify Activation

```bash
which python
```

* It should show:

```bash
.../venv/bin/python
```

### 4. How to share a project without version conflicts?

```bash
pip list 
```

* Shows all the packages and their versions installed in the virtual environment.

```bash
pip freeze > requirements.txt
```

* Creates a file called **requirements.txt** that contains all the packages along with their versions required for the project.

### 5. Deactivate Virtual Environment

```bash
deactivate
```

* This command deactivates the virtual environment and restores `PATH` and other environment variables to their state before activation.

## Summary

* **Virtual environment** is a separate space to manage project-specific packages.
* **Activate** enables the virtual environment and applies necessary changes.
* **Source** runs a script in the current shell session.
* **printenv** displays all environment variables in the current shell session.
* **$PATH** is a list of directories where Linux looks for executable programs.
  
