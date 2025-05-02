# FurWare Issue Tracker Repo

This repository doesn't contain source code. Our source code is stored on Nova's Git server, which is linked below. To submit Pull Requests/Code Changes, please generate a patch using the guide below.

## Links

**All Repos:** http://git.novafurry.win/os

## Patch Guide

1.  **Clone the Repository**

    We assume you know how to do this, but here are some important notes:

    * If you're not an internal collaborator, use HTTP to clone for security.

    **Example command to clone the example implementation:**

    ```bash
    git clone [http://git.novafurry.win/os/example-implementation](http://git.novafurry.win/os/example-implementation)
    ```

    * Internal collaborators, please use your Devbox for all programming. When cloning, use the Devbox's UI tool. This uses the internal IP (make sure the WG VPN is on!).

2.  **Create a Local Branch**

    * Before making any modifications, create a new branch to isolate your changes. This makes it easier to manage and submit your work. Choose a descriptive name for your branch. You can create a branch using the command below:

    ```bash
    git checkout -b feature/your-feature-name
    ```

3.  **Make the Changes**

    Now, make the necessary modifications to the codebase using your preferred editor.

4.  **Stage and Commit Your Changes**

    * Once you've made your changes, stage them for commit using the `git add` command. You can add specific files or all changed files:

    ```bash
    git add .
    ```

    * Commit your staged changes with a clear and concise commit message explaining what you've done:

    ```bash
    git commit -m "feat: Add your awesome feature"
    ```

    * Follow good commit message conventions (e.g., using a prefix like `feat`, `fix`, `docs`, etc., and a brief summary).

5.  **Generate the Patch File**

    * After committing your changes, you need to generate a patch file. This file contains the differences between your branch and the `main` (or `master`) branch of our repository. Ensure you are on your feature branch:

    ```bash
    git checkout feature/your-feature-name
    ```

    * Then, generate the patch. You'll typically want to generate a patch against the `main` branch of your local repository:

    ```bash
    git format-patch main -o patches
    ```

    >   [!TIP]
    >   Replace `main` with the name of the upstream branch. We use `main` by default.
    >   [!IMPORTANT]
    >   You will find the patch in the `patches` directory, relative to the directory in which you ran the command.

6.  **Submitting Your Patch**

    * Create an issue explaining your patch, and upload the file to the issue by dragging and dropping.
    * Do not update your local repository until the team has approved and implemented or denied your patch.
