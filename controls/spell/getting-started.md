---
title: Getting Started
page_title: Getting Started | UI for ASP.NET AJAX Documentation
description: Getting Started
slug: spell/getting-started
tags: getting,started
published: True
position: 2
---

# Getting Started



## 

The following tutorial demonstrates using RadSpell to spell check a standard ASP.NET TextBox control using either an English or French dictionary. The walk-through will also show how to change the skin of the spell check dialog.
>caption 

![](images/spell-gettingstarted003b.png)

1. In the default page of a new __ASP.NET AJAX-enabled Web Application__ add a TextBox control and a RadSpell control.

1. In the Solution Explorer, right-click the project and select Add | Add ASP.NET Folder | App_GlobalResources.

1. In the Solution Explorer, right-click the project and select Add | Add ASP.NET Folder | App_Data.

1. Locate the App_GlobalResources and App_Data folders in your Telerik UI for ASP.NET AJAXTelerik UI installation folder.

1. Copy the App_Data\RadSpell to the project's \App_Data folder.

1. Copy the App_GlobalResources\RadSpell.Dialog.resx to the project's \App_GlobalResources folder.

1. The project structure should now look like the screenshot below.
>caption 

![](images/spell-gettingstarted001.png)

1. Set the TextBox __Text__ property to "mispleng";

1. Open the RadSpell [Smart Tag]({%slug spell/design-time%}) and select the __Vista__[Skin]({%slug spell/appearance-and-styling/skins%}) from the drop down menu. Select the __Enable RadSpell Http Handlers__ link. Click __OK__ to close the confirmation dialogs for the spell check and dialog handlers.
>caption 

![](images/spell-gettingstarted002.png)

1. In the Properties Window for the RadSpell control set the following properties:

* __ButtonType__ = __LinkButton__

* __ButtonText =__ "Click this link to spell check"

* __ControlToCheck =__ "TextBox1"

* __SupportedLanguages__ = en-US,English,fr-FR,French"

1. Press __F5__ to run the application. Use the drop down list to select English or French and notice the change in selected words.
>caption 

![](images/spell-gettingstarted003.png)
