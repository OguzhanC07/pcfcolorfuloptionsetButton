
# Control Overview
This control is an OptionSet control for model driven app (D365), which will display all options as clickable buttons with colorful background set for the options inside OptionSet. It is best works for alert types or Yes No optionsets with color coding. This control dynamically sets the buttons based on options in optionset.

# Install
 - Download the latest version of the solution from solution folder !
 - Import the solution to your Dynamics 365 instance


# Debugging and Creating Your Own Version

## Steps to Follow

### 1. Install Dependencies
Run the following command to install necessary packages:
```sh
npm install
```

### 2. Build the Project
Execute this command to start the build process:
```sh
npm start build
```

### 3. Create the `Solutions` Folder
A `Solutions` folder already exists in the repository, but if you're customizing, you must delete it first and then recreate it manually.

### 4. Initialize the Solution
Inside the `Solutions` folder, run the following command to initialize the solution:
```sh
pac solution init --publisher-name developer --publisher-prefix dev
```
> **Note:** Replace `developer` with your desired publisher name and `dev` with your preferred prefix.

### 5. Add a Reference to the Component
Run this command inside the `Solutions` folder:
```sh
pac solution add-reference --path c:\downloads\mysamplecomponent
```
> **Note:** Provide the correct main path of your project.

### 6. Handle Potential Errors
If an error occurs, add the following lines to your `Solutions.cdsproj` file:
```xml
<ItemGroup>
    <ProjectReference Include="..\ColorfulOptionSet.pcfproj" />
</ItemGroup>
```

### 7. Restore Dependencies
Inside the `Solutions` folder, run:
```sh
msbuild /t:restore
```

### 8. Modify `.cdsproj` File (Optional)
Inside the `.cdsproj` file, there is an option to create both **managed** and **unmanaged** versions of the solution. You can modify the `SolutionPackageType` property according to your needs.

### 9. Build the Solution
Run the following command inside the `Solutions` folder:
```sh
msbuild /p:configuration=Release
```

### 10. Locate the Built Solution
After completing the build, the solution will be located in:
```
Solutions\bin\Release
```

### 11. Upgrade Version
To upgrade the version, update the version number in these files:
- `ControlManifest.Input.xml`
- `Solutions\src\Other\Solution.xml`

Make sure both files have the correct version for consistency.

---


## Control Registration Steps 
 - After import of the control the control is available in the list of available controls
![alternativetext](readmeimages/imgOptionSetControlSelect.png)

![alternativetext](readmeimages/imgOptionsetcontrol.png)

## OptionSet Color Configuration
To set the color of the optionset buttons configure the color in optionset attribute

![alternativetext](readmeimages/imgoptionsetcolorconfiguration.png)
