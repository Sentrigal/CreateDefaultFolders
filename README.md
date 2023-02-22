# CreateDefaultFolders
Small setup to quickly create a default folder layout for your Unity project.


Included are two scripts that you can store anywhere in your Unity project. Once they're included, you will find a new button under "Assets", called "Create Default Folders". Clicking it will open a window where you can enter a name for your root folder, decide whether dummy files should be created and with another button press the hardcoded folder structure will be created at the root (/Assets/) of your project. 

To change this default, hardcoded structure, open up CreateFolderStructure.cs and scroll down to the CreateFolders() method to find a quick explanation and the code. The provided "VirtualFolder" struct makes it fairly straight forward to layout this structure.

First, create a rootFolder like so:
VirtualFolder rootFolder = new VirtualFolder("Assets", rootFolderName); "rootFolderName" contains the name you enter in the Unity window.

After that, you can simply add more folders to this one by calling AddSubFolder() on it, like so:
rootFolder.AddSubFolder("SubFolderName");
You can also chain these like so:
rootFolder.AddSubFolder("SubFolderName").AddSubFolder("YetAnotherFolder");

Creating your own layout should be fairly quick. Just save the script, hit up the button again and poof, folders.

The default, hardcoded layout looks like this:

![Structure](https://i.imgur.com/mtMnD8w.png)

As you can see, the folders are also not empty, that's because I checked the dummy file checkbox. This creates a little textfile whose only purpose is to add the folder to a commit (since empty folders are ignored). Once there is actual data in it, you can just delete it.
