---
layout: Conceptual
title: Custom Headers &lt;customHeaders&gt; | Microsoft Learn
canonicalUrl: https://learn.microsoft.com/en-us/iis/configuration/system.webserver/httpprotocol/customheaders/
ms.service: iis
feedback_system: Standard
feedback_help_link_type: get-help-at-qna
feedback_help_link_url: https://learn.microsoft.com/answers/tags/85/windows-iis
breadcrumb_path: /iis/breadcrumb/toc.json
uhfHeaderId: MSDocsHeader-Windows
ms.topic: reference
author: Rick-Anderson
ms.author: gewarren
ms.subservice: config-reference
ms.update-cycle: 3650-days
description: Overview The &lt;customHeaders&gt; element of the &lt;httpProtocol&gt; element specifies custom HTTP headers that Internet Information Services (IIS) 7 will...
ms.date: 2016-09-26T00:00:00.0000000Z
ms.assetid: c6cedc17-5db1-4a74-935f-ba286d203d3e
msc.legacyurl: /configreference/system.webserver/httpprotocol/customheaders
msc.type: config
locale: en-us
document_id: a44e6c00-f124-5d26-228d-ac2889521521
document_version_independent_id: 38dd78d8-6e1d-c58b-f854-6f33c31660ea
updated_at: 2022-04-06T20:16:00.0000000Z
original_content_git_url: https://github.com/MicrosoftDocs/iis-docs/blob/live/iis/configuration/system.webServer/httpProtocol/customHeaders/index.md
gitcommit: https://github.com/MicrosoftDocs/iis-docs/blob/9026fbda23de185af79e4da5b151a5fbbd9af75d/iis/configuration/system.webServer/httpProtocol/customHeaders/index.md
git_commit_id: 9026fbda23de185af79e4da5b151a5fbbd9af75d
site_name: Docs
depot_name: MSDN.IIS
page_type: conceptual
toc_rel: ../../../toc.json
pdf_url_template: https://learn.microsoft.com/pdfstore/en-us/MSDN.IIS/{branchName}{pdfName}
feedback_product_url: ''
word_count: 673
asset_id: configuration/system.webserver/httpprotocol/customheaders/index
moniker_range_name: 
monikers: []
item_type: Content
source_path: iis/configuration/system.webServer/httpProtocol/customHeaders/index.md
cmProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/fc3f72c2-fb6f-4cea-95ee-b444e52254ee
- https://authoring-docs-microsoft.poolparty.biz/devrel/bcbcbad5-4208-4783-8035-8481272c98b8
spProducts:
- https://microsoft-devrel.poolparty.biz/DevRelOfferingOntology/f12cf087-582d-48ac-a085-0c19adf1e391
- https://authoring-docs-microsoft.poolparty.biz/devrel/43b2e5aa-8a6d-4de2-a252-692232e5edc8
platformId: 414d34a8-40e1-e907-7a44-230576b262c4
---

# Custom Headers &lt;customHeaders&gt; | Microsoft Learn

## Overview

The `<customHeaders>` element of the `<httpProtocol>` element specifies custom HTTP headers that Internet Information Services (IIS) 7 will return in HTTP responses from the Web server.

Note

HTTP headers are name and value pairs that are returned in responses from a Web server. Custom response headers are sent to the client together with the default HTTP header. Unlike redirect response headers, which are returned in responses only when redirection occurs, custom response headers are returned in every response.

## Compatibility

| Version | Notes |
| --- | --- |
| IIS 10.0 | The `<customHeaders>` element was not modified in IIS 10.0. |
| IIS 8.5 | The `<customHeaders>` element was not modified in IIS 8.5. |
| IIS 8.0 | The `<customHeaders>` element was not modified in IIS 8.0. |
| IIS 7.5 | The `<customHeaders>` element was not modified in IIS 7.5. |
| IIS 7.0 | The `<customHeaders>` element of the `<httpProtocol>` element was introduced in IIS 7.0. |
| IIS 6.0 | The `<customHeaders>` element replaces the IIS 6.0 **HttpCustomHeaders** metabase object. |

## Setup

The `<customHeaders>` element of the `<httpProtocol>` element is included in the default installation of IIS 7.

## How To

### How to set custom HTTP headers for a Web site or application

1. Open **Internet Information Services (IIS) Manager**:

    - If you are using Windows Server 2012 or Windows Server 2012 R2:

        - On the taskbar, click **Server Manager**, click **Tools**, and then click **Internet Information Services (IIS) Manager**.
    - If you are using Windows 8 or Windows 8.1:

        - Hold down the **Windows** key, press the letter **X**, and then click **Control Panel**.
        - Click **Administrative Tools**, and then double-click **Internet Information Services (IIS) Manager**.
    - If you are using Windows Server 2008 or Windows Server 2008 R2:

        - On the taskbar, click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.
    - If you are using Windows Vista or Windows 7:

        - On the taskbar, click **Start**, and then click **Control Panel**.
        - Double-click **Administrative Tools**, and then double-click **Internet Information Services (IIS) Manager**.
2. In the **Connections** pane, go to the site, application, or directory for which you want to set a custom HTTP header.
3. In the **Home** pane, double-click **HTTP Response Headers**.[![Screenshot that shows the Home pane with H T T P Response Headers selected.](index/_static/image2.png)](index/_static/image1.png)
4. In the **HTTP Response Headers** pane, click **Add...** in the **Actions** pane.[![Screenshot of H T T P Response Headers pane with Add option displayed in the Actions pane.](index/_static/image4.png)](index/_static/image3.png)
5. In the **Add Custom HTTP Response Header** dialog box, set the name and value for your custom header, and then click **OK**.[![Screenshot of Add Custom H T T P Header dialog box with fields for name and value for custom header.](index/_static/image6.png)](index/_static/image5.png)

## Configuration

### Attributes

None.

### Child Elements

| Element | Description |
| --- | --- |
| [`add`](add) | Optional element.Adds a custom response header to the `<customHeaders>` collection. |
| `clear` | Optional element.Removes all references to custom response headers from the `<customHeaders>` collection. |
| `remove` | Optional element.Removes a reference to a custom response header from the `<customHeaders>` collection. |

### Configuration Sample

The following configuration sample sets a custom HTTP header and value.

```xml
<configuration>
   <system.webServer>
      <httpProtocol>
         <customHeaders>
            <add name="X-Custom-Name" value="MyCustomValue" />
         </customHeaders>
      </httpProtocol>
   </system.webServer>
</configuration>
```

Note

The following default `<httpProtocol>` element is configured in the ApplicationHost.config file in IIS 7.

```xml
<httpProtocol>
   <customHeaders>
      <clear />
      <add name="X-Powered-By" value="ASP.NET" />
   </customHeaders>
   <redirectHeaders>
      <clear />
   </redirectHeaders>
</httpProtocol>
```

## Sample Code

The following code samples set a custom HTTP header and value.

### AppCmd.exe

```console
appcmd.exe set config "Default Web Site" -section:system.webServer/httpProtocol /+"customHeaders.[name='X-Custom-Name',value='MyCustomValue']"
```

### C#

```csharp
using System;
using System.Text;
using Microsoft.Web.Administration;

internal static class Sample
{
   private static void Main()
   {
      using (ServerManager serverManager = new ServerManager())
      {
         Configuration config = serverManager.GetWebConfiguration("Default Web Site");
         ConfigurationSection httpProtocolSection = config.GetSection("system.webServer/httpProtocol");
         ConfigurationElementCollection customHeadersCollection = httpProtocolSection.GetCollection("customHeaders");

         ConfigurationElement addElement = customHeadersCollection.CreateElement("add");
         addElement["name"] = @"X-Custom-Name";
         addElement["value"] = @"MyCustomValue";
         customHeadersCollection.Add(addElement);

         serverManager.CommitChanges();
      }
   }
}
```

### VB.NET

```vb
Imports System
Imports System.Text
Imports Microsoft.Web.Administration

Module Sample

   Sub Main()
      Dim serverManager As ServerManager = New ServerManager
      Dim config As Configuration = serverManager.GetWebConfiguration("Default Web Site")
      Dim httpProtocolSection As ConfigurationSection = config.GetSection("system.webServer/httpProtocol")
      Dim customHeadersCollection As ConfigurationElementCollection = httpProtocolSection.GetCollection("customHeaders")

      Dim addElement As ConfigurationElement = customHeadersCollection.CreateElement("add")
      addElement("name") = "X-Custom-Name"
      addElement("value") = "MyCustomValue"
      customHeadersCollection.Add(addElement)

      serverManager.CommitChanges()
   End Sub

End Module
```

### JavaScript

```javascript
var adminManager = new ActiveXObject('Microsoft.ApplicationHost.WritableAdminManager');
adminManager.CommitPath = "MACHINE/WEBROOT/APPHOST/Default Web Site";
var httpProtocolSection = adminManager.GetAdminSection("system.webServer/httpProtocol", "MACHINE/WEBROOT/APPHOST/Default Web Site");
var customHeadersCollection = httpProtocolSection.ChildElements.Item("customHeaders").Collection;

var addElement = customHeadersCollection.CreateNewElement("add");
addElement.Properties.Item("name").Value = "X-Custom-Name";
addElement.Properties.Item("value").Value = "MyCustomValue";
customHeadersCollection.AddElement(addElement);

adminManager.CommitChanges();
```

### VBScript

```vb
Set adminManager = WScript.CreateObject("Microsoft.ApplicationHost.WritableAdminManager")
adminManager.CommitPath = "MACHINE/WEBROOT/APPHOST/Default Web Site"
Set httpProtocolSection = adminManager.GetAdminSection("system.webServer/httpProtocol", "MACHINE/WEBROOT/APPHOST/Default Web Site")
Set customHeadersCollection = httpProtocolSection.ChildElements.Item("customHeaders").Collection

Set addElement = customHeadersCollection.CreateNewElement("add")
addElement.Properties.Item("name").Value = "X-Custom-Name"
addElement.Properties.Item("value").Value = "MyCustomValue"
customHeadersCollection.AddElement(addElement)

adminManager.CommitChanges()
```
