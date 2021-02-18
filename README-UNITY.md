# Package for Unity 3d

### 1. Fork from upstream repo `RevenantX/LiteNetLib`
Fork from upstream repo `RevenantX/LiteNetLib`, then clone it, reset it to a release, and push it.

	git clone https://github.com/dustorg/LiteNetLib.git
	git reset --hard 0.9.4
	git push --force origin master

### 2. Make changes for Unity 3d
Delete `./LiteNetLib/LiteNetLib.csproj`

### 3. Add Unity package manifest to `./LiteNetLib/package.json`
    {
      "name": "com.github.revenantx.litenetlib",
      "version": "0.9.4",
      "displayName": "LiteNetLib",
      "description": "RevenantX/LiteNetLib packaged for Unity"
    }

### 4. Generate Unity meta files
For some reason Unity can't just use a git url, you have to:
1. Create a dummy Unity project
2. Add the library sources to it you want to use (the `./LiteNetLib/` directory in this case)
3. Let the Unity editor generate the meta files
4. Drag the files back into the git repo. 
5. Remove the `*.meta` from `.gitignore` so they're picked up in the final commit.
6. Cry
7. Add an Assembly Definition file named `LiteNetLib`

### 5. Commit
    git add -A && git commit -am "Package for Unity"
    git push origin master

### 6. Use in Unity
Then use the following link in Unity's Package Manager:
`https://github.com/dustorg/LiteNetLib.git?path=/LiteNetLib`
