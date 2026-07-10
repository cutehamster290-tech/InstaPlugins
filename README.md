# InstaPlugins
A new Roblox Framework.

# What is InstaPlugins
InstaPlugins is a Luau Plugin that makes Scalable and Efficient the creation of Plugins, it is inspired from ReactJs. It is easy to import, config and init.

# Usage:

## How to set it up
When you run InstaPlugins in Roblox Studio you need to choose a Name for the Plugin and choose a place where to import the Framework (i suggest ServerScriptService), you can also toggle turn on/off the Shortcuts, which lets you can write !setup or similiar keywords in LuaSourceContainers.

## How to start using it
Once you configured it, you can see that the folder you created for your Plugin will have a ModuleScript, a Script and a Folder (Components), you will be using most of the times the Script and the Folder, to Connect the Instances you make into the Scipt, as i already said, it is inspired from ReactJs. You can create Module scripts in the Components Folder which returns a function with atleast 2 arguments: Component (Instance or pluginButtonData) and Data (a Table or Dictionary). **Now this Structure lets you can manage multiple similiar Buttons or Instances at the same time with just sending those 2 arguments, and calling the same function, and having more Clear code**, this is one of a cool features my plugin gives to you.

## Data Saving
my plugin dont lose important data, when you create a Toolbar or you create a pluginButton your data will be saved, a feature that can be lost if not stored in variables, my plugin does it automatically, and if you want your plugin to be fast you can use the root:SaveData(false) which will not store unnecessary data, or the data you specify, by the way, :SaveData lets you can toggle save/not save data or specified data if you provide another agument followed after the boolean.
Now, as i said, my plugin saves data automatically, **but how to acess it**? when you create a Button for your Toolbar, you can acess the data of it, a feature that the plugin keyword dont provide, after you created the Button using root:CreateButton you provide the Id, Tooltip, IconImg, Description and Toolbar.

## Useful Commands
  1) the `root:Init({Component: pluginButtonData, ModuleScript: ModuleScript, Data: {}?, elaborateData: boolean?})` lets you can Initialize a module script, you need pass a Component and a ModuleScript to this function, and if you want, Data and elaborateData, and the Main script will call the function you returned from that Module Script passing the data (Data and elaborateData) as Arguments.
**elaborateData**: Converts a Dictionary to a Table, you can see that when you import the Main Folder, there is a ModuleScript (Component) inside Components where you see that i am getting Data[1] and not Data['Text'] which is what i sent from the Plugin Script, **this might be dangerous if not handled correctly**.
  2) `root:Config(Folder:Folder)` is a function that returns the Components Folder and the Name of the Folder, but at the same time saves the Main Folder and the Components Folder and the Main Folder Name in root, you can acess them using `root.MainFolder root.Components root.Name`
  3) `root:Get(Name:string, place:'Components'|'MainFolder'|Instance?` returns the first Instance found with name Name and in place or by default in Components.

# Future Updates
- `root:SaveData(value:boolean)` will soon have the ability to toogle save/not save data of specified fields of Data, by inserting as second argument a Dictionary, this will help you manage the data faster and make the plugin more Efficient.
- GUI managing: You will be soon able to create Guis and DockWidgets faster.
