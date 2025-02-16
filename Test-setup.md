# Test Setup

Primary aim: document steps to test the "MarkPub Quickstart"
instructions.  

### 2025-02-15 - mptest02 notes

1. Copied contents of mpTestCollection to this directory

 - MarkPub initialization must precede GitHub repository setup
   - initialization installs a `.gitignore` file which is needed
     before Obsidian and Obsidian Git plugin is setup.
	 
 - Obsidian Git plugin can only be enabled in an existing Git repository

1.1. one simple way to enable MarkPub for a document collection  
 - install MarkPub Python package
 - Initialize the document collection folder using MarkPub
   N.B.: add CC License file to `markpub/templates` (TBD)
   TODO: put those steps here  
   TODO: add `.github/workflows/` directory to `templates` and add
   install of that directory to `markpub init` code

- make the document collection folder a GitHub repository
   TODO: put those steps here  
   - on `github.com` create a new repository with folder directory
     name (in this example `mptest02`)
	 Do not initialize it with a README, license, or .gitignore files when creating it on GitHub.
   - on your computer
	 - CLI steps (in a Terminal app):  
 ```shell
 # 1. Navigate to the document collection directory
cd /path/to/document-directory

# 2. Initialize a new git repository
git init

# 3. Add all files to staging
git add .

# 4. Commit the files
git commit -m "Initial commit"

# 5. Create a new repository on GitHub (this must be done manually on GitHub.com)
# Then, add the remote repository URL
git remote add origin https://github.com/username/document-directory.git

# 6. Rename the default branch to 'main' (if needed)
git branch -M main

# 7. Push your code to GitHub
git push -u origin main
```

 - TODO: set up a web deployment service (GitHub Pages)
	 put those steps here  

 - VERIFY GitHub Pages deployment

 - TEST: update the repository content with a new page or changes to
   an existing page  
   - Git "commit" and "push" the updated pages  
   VERIFY GitHub Pages deployment is updated  


2. OPTIONAL: Make it an Obsidian vault  
DONE: create some wiki-links ...  
TODO: install ObsidianGit plugin  
 - note: ObsidianSync plugin enabled by default?  - DISABLE

4. Test deployment  

TODO: separate this into two documents  
- one for pre-MarkPub install and init  
- one to test the MarkPub install and use instructions  

-----
2025-02-04: testing a simple GitHub pages deployment:  
 (1): directory previously set up as a GitHub repository  
 (2): `markpub init directory-name`  
```shell
cd directory-name
git add .
git commit -m "MarkPub initialization"
git push
```  
 (3): copied `.github/` directory from an existing document-collection
 repository  
   - edited the `.github/workflows/gh-pages.yml` file and inserted
     this repository's name into the `markpub build ...` command  
```shell
git add .github/
git commit -m "GitHub pages config files"
git push
```  
 (4) logged into GitHub, and for this repository's "Pages" settings,
 set "Build and deployment" "Branch" to "gh-pages" in the drop-down
 menu, and "Save" that setting  
  - Saving that setting triggers and "pages build and deployment"
    workflow under the "Actions" tab  
  - when completed the website is available at:  
  <https://githubaccountname.github.io/repositoryname>  
  (in this example this is https://band.github.io/mptestcollection)  


