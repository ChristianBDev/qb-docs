---
description: Learn how to use exports to update the shared dynamically!
---

# ↗ Shared Exports

<table>
    <thead>
        <tr>
            <th>Function or Event</th>
            <th width="150">Scope</th>
            <th width="207">Description</th>
            <th>Returns</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td align="center">exports['qb-core']:AddItem(itemName, item)</td>
            <td align="center">Server</td>
            <td align="center">Accepts an item name and item object - will add new entry to QBCore.Shared.Items</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:AddItems(items)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Items</td>
            <td align="center">boolean, string, errorItem</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:UpdateItem(itemName, item)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Items</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:RemoveItem(itemName)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Items</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:AddJob(jobName, job)</td>
            <td align="center">Server</td>
            <td align="center">Accepts an job name and job object - will add new entry to QBCore.Shared.Jobs</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:AddJobs(jobs)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Jobs</td>
            <td align="center">boolean, string, errorItem</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:UpdateJob(jobName, job)</td>
            <td align="center">Server</td>
            <td align="center">Accepts an job name and job object - will add new entry to QBCore.Shared.Jobs</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:RemoveJob(jobName)</td>
            <td align="center">Server</td>
            <td align="center">Accepts an job name and job object - will add new entry to QBCore.Shared.Jobs</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:AddGang(gangName, gang)</td>
            <td align="center">Server</td>
            <td align="center">Accepts an gang name and gang object - will add new entry to QBCore.Shared.Gangs</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:AddGangs(gangs)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Gangs</td>
            <td align="center">boolean, string, errorItem</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:UpdateGang(gangName, gang)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Gangs</td>
            <td align="center">boolean, string</td>
        </tr>
        <tr>
            <td align="center">exports['qb-core']:RemoveGang(gangName)</td>
            <td align="center">Server</td>
            <td align="center">Accepts a table or array - will loop through the table and add new entries to QBCore.Shared.Gangs</td>
            <td align="center">boolean, string</td>
        </tr>
    </tbody>
</table>

## Import Jobs

-   This method allows for any resource to insert job data into the shared file for the core. That means that you can make a resource, and on load, make those jobs available for use. This can be accomplished through one the ways shown below. Utilizing the function requires importing the core but using the export does not

{% hint style="danger" %}
Read over and learn the [shared.md](shared.md "mention") structure before attempting to use these
{% endhint %}

{% hint style="warning" %}
You must add this code to the client-side or server-side file(s) of your resource when using these if you need the core object!
{% endhint %}

```lua
local QBCore = expors['qb-core']:GetCoreObject()
```

### QBCore.Functions.AddJob

```lua
QBCore.Functions.AddJob(jobName --[[string]], job --[[table]])

-- Example
QBCore.Functions.AddJob('unemployed', {
    label = 'Civilian',
    defaultDuty = true,
    offDutyPay = false,
    grades = {
        ['0'] = {
            name = 'Freelancer',
            payment = 10
        }
    }
})
```

### QBCore.Functions.AddJobs

```lua
QBCore.Functions.AddJobs(jobs --[[table]])

-- Example
QBCore.Functions.AddJobs({
    ['unemployed'] = {
        label = 'Civilian',
        defaultDuty = true,
        offDutyPay = false,
        grades = {
            ['0'] = {
                name = 'Freelancer',
                payment = 10
            }
        }
    },
    ['trucker'] = {
        label = 'Trucker',
        defaultDuty = true,
        offDutyPay = false,
        grades = {
            ['0'] = {
                name = 'Driver',
                payment = 50
            }
        }
    }
})
```

## Import Gangs

-   This method allows for any resource to insert gang data into the shared file for the core. That means that you can make a resource, and on load, make those gangs available for use. This can be accomplished through one the ways shown below. Utilizing the function requires importing the core but using the export does not

### QBCore.Functions.AddGang

```lua
QBCore.Functions.AddGang(gangName --[[string]], gang --[[table]])

-- Example
QBCore.Functions.AddGang('azteca', {
    label = 'Azteca',
    grades = {
        ['0'] = {
            name = 'Recruit'
        }
    }
})
```

### QBCore.Functions.AddGangs

```lua
QBCore.Functions.AddGangs(gangs --[[table]])

-- Example
QBCore.Functions.AddGangs({
    ['lostmc'] = {
        label = 'Lost MC',
        grades = {
            ['0'] = {
                name = 'Recruit'
            }
        }
    },
    ['ballas'] = {
        label = 'Ballas',
        grades = {
            ['0'] = {
                name = 'Recruit'
            }
        }
    }
})
```

## Import Items

-   This method allows for any resource to insert item data into the shared file for the core. That means that you can make a resource, and on load, make those items available for use. This can be accomplished through one the ways shown below. Utilizing the function requires importing the core but using the export does not

### QBCore.Functions.AddItem

```lua
QBCore.Functions.AddItem(itemName --[[string]], item --[[table]])

-- Example
QBCore.Functions.AddItem('water_bottle', {
    name = 'water_bottle',
    label = 'Bottle of Water',
    weight = 10,
    type = 'item',
    image = 'water_bottle.png',
    unique = false,
    useable = true,
    shouldClose = true,
    combinable = nil,
    description = 'For all the thirsty out there'
})
```

### QBCore.Functions.AddItems

```lua
QBCore.Functions.AddItems(items --[[table]])

-- Example
QBCore.Functions.AddItems({
    ['water_bottle'] = {
        name = 'water_bottle',
        label = 'Bottle of Water',
        weight = 10,
        type = 'item',
        image = 'water_bottle.png',
        unique = false,
        useable = true,
        shouldClose = true,
        combinable = nil,
        description = 'For all the thirsty out there'
    },
    ['sandwich'] = {
        name = 'sandwich',
        label = 'Sandwich',
        weight = 10,
        type = 'item',
        image = 'sandwich.png',
        unique = false,
        useable = true,
        shouldClose = true,
        combinable = nil,
        description = 'Nice bread for your stomach'
    }
})
```
