---
title: CustomTab element in the manifest file
description: On the ribbon, you specify which tab and group for their add-in commands.
ms.date: 01/24/2020
localization_priority: Normal
---

# CustomTab element

On the ribbon, you specify which tab and group for their add-in commands. This can either be on the default tab (either **Home**, **Message**, or **Meeting**), or on a custom tab defined by the add-in.

On custom tabs, the add-in can create up to 10 groups. Each group is limited to 6 controls, regardless of which tab it appears on. Add-ins are limited to one custom tab.

The **id** attribute must be unique within the manifest.

> [!IMPORTANT]
> In Outlook on Mac, the `CustomTab` element is not available so you'll have to use [OfficeTab](officetab.md) instead.

## Child elements

|  Element |  Required  |  Description  |
|:-----|:-----|:-----|
|  [Group](group.md)      | Yes |  Defines a Group of commands.  |
|  [Label](#label-tab)      | Yes |  The label for the CustomTab or a Group.  |

### Group

Required. See [Group element](group.md).

### Label (Tab)

Required. The label of the custom tab. The **resid** attribute must be set to the value of the **id** attribute of a **String** element in the **ShortStrings** element in the [Resources](resources.md) element.


## CustomTab example

```xml
<ExtensionPoint xsi:type="MessageReadCommandSurface">
  <CustomTab id="TabCustom1">
    <Group id="msgreadCustomTab.grp1">
    </Group>
    <Label resid="customTabLabel1"/>
  </CustomTab>
</ExtensionPoint>
```
