# Analysis and Visualization of Complex Agro-Environmental Data

## Instructions to use git and github to upload your personal documents and exercises into the AVCAD Course repository

---
The AVCAD Course repository is located here: https://github.com/isa-ulisboa/greends-avcad-2024


### Step 1 - Fork a copy of the repository into your personal page

There is no git fork command, so this step must be done in github. Go to the github repositoy that you intend to fork and simply use the button at the top right of the screen, and click on the green button "create fork".

In your new personal branch, you will need first to create a sub-folder with your name in the existing "people" folder using the button "add file" located in the right side of github and writing your name followed by a bar ("yourname"/), then you will need to create a new empty file (e.g. readme) otherwise it is not possible to create a sub-folder. After that you may upload your exercises to that sub-folder using git commands or vscode and then do a pull request in github ("open pull request" and then "create pull request").


### Step 2 - Clone the repository to you local machine

In the CLI terminal (bash or powershell), go to the folder where your clone will be located and run the following command in a CLI terminal (bash or powershell)
```
$ git clone <repo_url>
```
You may want just to clone a single folder:
```
$ git clone <repo_url> <dir_name>
```

### Step 3 - Update your fork

Whenever a new exercise, example or another document where you will make your personal changes is available on the course repository, update your fork by clicking on "Sync fork".

### Step 4 - Pull changes into your local machine

In the CLI terminal (bash or powershell), enter the cloned folder and run:
```
$ git pull
```

### Step 5 - Introduce changes and commit

Copy the new file(s) into your folder and make the requested changes (solve exercises, etc). Then commit your changes, by first adding the new changed file and then commiting the changes. In the CLI terminal (bash or powershell), enter the cloned folder and run:
```
$ git add .
$ git commit -m "message"
```

### Step 5 - Push your changes into the remote machine

Run:
```
$ git push origin main
```

### Step 6 - Make a pull request to the original repository

In github click on "open pull request" -> "create pull request".

---
### Return to step 3 whenever a change has been made into the original repository.


