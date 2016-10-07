# Override Default Structure Browser

The Override Default Structure Browser project contains five (5) import packages, each providing sample code for customizing the Structure Browser view in Aras. Here is a brief description of the scenario addressed by the sample code in each import package.

#### 1. Default Structure Browser
This import package contains the default Structure Browser Method and can be used for rolling back changes or diffing changes.

**Note:** The Default Structure Browser package does **not** eliminate the need for a database backup before importing any of the Override Default Structure Browser packages. It is always considered best practice to backup your code tree and database before applying any changes to your environment.

#### 2. Add Property for Context ItemType
This package adds the Classification property to all items of the same type as the context item.

**Example:** When viewing the Structure Browser for a Part item, the context item and all child Parts will display their classification in the Structure Viewer. Other child items, such as CAD items or Documents, will not display any custom property values.

#### 3. Add Property for Specified ItemTypes
This package adds the Classification property to all items displayed in the Structure Browser.

**Example:** When viewing the Structure Browser for a Part item, the context item and child items of any type will display their classification in the Structure Viewer.

#### 4. Filter Relationships
This package filters the type of child items displayed in the Structure Browser. Additionally, it defines different properties to display depending on an item's type.

**Example:** When viewing the Structure Browser for a Part Item, only the CAD and Document child items will be displayed. The context item will be displayed with its classification value, and the child items will be displayed with their state values.

#### 5. Customize Images Loaded
This package customizes the icon displayed with each item in the Structure Browser based on a specific property value.

**Example:** When viewing the Structure Browser, Parts in the "Released" state will be displayed with one custom icon and Parts in the "Preliminary" state will be displayed with a second custom icon. All other Part items will be displayed with the default ItemType icon.

## Project Details

**Built Using:** Aras 11.0 SP7
**Browsers Tested:** Internet Explorer 11, Firefox 38 ESR, Chrome

> Though built and tested using Aras 11.0 SP7, this project may function in older releases of Aras 11.0 and Aras 10.0.

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed (version 11.0 SPx preferred)
2. Aras Package Import tool
3. Override Default Structure Browser import package(s)

### Install Steps

> Note: Install project packages one at a time.
> Each package modifies the same Method item, so the last package imported will always overwrite the changes made by any others.

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
  * _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
  * Optional: Enter a description in the Description field.
5. Enter the path to your local `..\OverrideDefaultStructureBrowser\Import\<PackageName>\imports.mf` file in the Manifest File field.
6. Select **com.aras.innovator.core** in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

You are now ready to login to Aras and try a custom Structure Browser view.

## Usage

1. Login to Aras.
2. Navigate to your target ItemType in the Table of Contents (TOC).
3. Search for your target item in the main grid.
4. Select your target item in the main grid.
5. Right click the target item and select **Structure Browser**.

The Structure Browser will appear according to the customizations defined by the installed Override Default Structure Browser package. You can view the customization code in the ``GetItemsForStructureBrowser`` Method item.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

For more information on contributing to this project, another Aras Labs project, or any Aras Community project, shoot us an email at araslabs@aras.com.

## License

Aras Labs projects are published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
