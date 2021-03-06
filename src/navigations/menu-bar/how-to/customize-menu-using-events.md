---
title: "Customize Menu Bar Using Events"
component: "Menu Bar"
description: "This section helps to learn how to Customize Menu Bar Using Events."
---

# Customize Menu Bar Using Events

The Menu Bar provides a set of events to enable users to customize it.

The available events are [`OnOpen`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ContextMenuEvents-1.html#Syncfusion_Blazor_Navigations_ContextMenuEvents_1_OnOpen), [`OnClose`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ContextMenuEvents-1.html#Syncfusion_Blazor_Navigations_ContextMenuEvents_1_OnClose), [`Closed`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ContextMenuEvents-1.html#Syncfusion_Blazor_Navigations_ContextMenuEvents_1_Closed), [`Opened`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ContextMenuEvents-1.html#Syncfusion_Blazor_Navigations_ContextMenuEvents_1_Opened), and [`ItemSelected`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.ContextMenuEvents-1.html#Syncfusion_Blazor_Navigations_ContextMenuEvents_1_ItemSelected).

```csharp

@using Syncfusion.Blazor.Navigations

<SfMenu Items="MenuItems">
    <MenuEvents OnOpen="onOpen" OnClose="onClose" Opened="opened" Closed="closed" ItemSelected="itemSelected"></MenuEvents>
</SfMenu>
<div id="preview">@eventName Event Triggered</div>

@code{
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem{ Text = "File", Items = new List<MenuItem>{
            new MenuItem{ Text= "Open" },
            new MenuItem{ Text= "Save" },
            new MenuItem{ Text= "Exit" }}
    },
        new MenuItem{ Text = "Edit", Items = new List<MenuItem>{
            new MenuItem{ Text= "Cut" },
            new MenuItem{ Text= "Copy" },
            new MenuItem{ Text= "Paste" }}
    },
        new MenuItem{ Text = "View", Items = new List<MenuItem>{
            new MenuItem{ Text = "Toolbars" },
            new MenuItem{ Text = "Zoom" },
            new MenuItem{ Text = "Full Screen" }}
    },
        new MenuItem{ Text = "Tools", Items = new List<MenuItem>{
            new MenuItem{ Text= "Spelling & Grammar" },
            new MenuItem{ Text= "Customize" },
            new MenuItem{ Text= "Options" }}
    },
        new MenuItem{ Text = "Go" },
        new MenuItem{ Text = "Help" }
    };

    private string eventName = "No";
    private void onOpen()
    {
        this.eventName = "OnOpen";
    }

    private void onClose()
    {
        this.eventName = "OnClose";
    }

    private void opened()
    {
        this.eventName = "Opened";
    }

    private void closed()
    {
        this.eventName = "Closed";
    }

    private void itemSelected()
    {
        this.eventName = "ItemSelected";
    }
}

<style>
    #preview{
        float: right;
        padding: 0 350px 0 0;
    }
</style>

```

Output be like

![Menu Sample](./../images/menu-events.png)
