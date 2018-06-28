# sweetheart
Sweetheart is a free software tool intended to handle the administration and deployment of the Cuddlemuffin-Honeybunch database system.

## Thoughts

The simplicity of Cuddlemuffin and Honeybunch client opens doors to a UI based Cuddlemuffin tool with potential for generation of Honeybunch boilerplates.

Conflict Resolution, calls for a tool that can display conflicting object versions, and potentially merge them to the latest.

Even something as simple as editing a record requires bumping of version and generation of a solid uuid/v4 and that too calls for a tool.

Hence, Sweetheart.

## Bonus

As a bonus there is no better way to quickly review API than writing a UI tool that fully relies on it.

## The Stack

#### User Interaction Scenario: fill out a form and save data to server

1. [data-command](https://github.com/fantasyui-com/data-command) binds a button via --on click flag
2. [bogo](https://github.com/fantasyui-com/bogo) sends command down to server
3. [cuddlemuffin](https://github.com/fantasyui-com/cuddlemuffin) saves the object to disk, by creating a folder with object id, and json file with random filename inside it.
3. ws is used to send a packet to [bogo](https://github.com/fantasyui-com/bogo) on the client

#### Update UI Scenario: Get updated packets from server and update UI.

 1. [bogo](https://github.com/fantasyui-com/bogo) gets object via ws from the server
 2. [pookie](https://github.com/fantasyui-com/pookie) gets packet from bogo and filters it info branches of its tree.
 3. [enbuffer](https://github.com/fantasyui-com/enbuffer) will keep a view of data arriving through a branch.
 4. [atom-smasher](https://github.com/fantasyui-com/atom-smasher) will create a POJO plain old JavaScript Object (povered by Proxies)
 5. [reconcilers](https://github.com/fantasyui-com/reconcilers) will use data and html to update DOM.
