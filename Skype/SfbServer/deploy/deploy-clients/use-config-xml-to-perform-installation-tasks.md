---
title: 在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml 檔案指定其他安裝指示。
ms.openlocfilehash: dbf4c4ba4e652f4b777e0c901fee4ffb0ad68af3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121137"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作

**摘要：** 如何使用 Config.xml 檔案指定其他安裝指示。

雖然 Office 自訂工具 (OCT) 是自訂安裝的主要工具，但是系統管理員可以使用 Config.xml 檔案來指定 OCT 中所沒有的其他安裝指示。下列自訂只能使用 Config.xml 檔案來進行：

- 指定網路安裝點的路徑。

- 選取所要安裝的產品。

- 設定安裝程式自訂檔案和軟體更新的記錄及位置。

- 指定安裝選項，例如使用者名稱。

- 將本機安裝來源 (LIS) 複製到使用者的電腦，而不安裝 Office。

- 在安裝中新增或移除語言。

建議您使用 Config.xml 檔案來設定商務用 Skype 無訊息安裝。 

根據預設，儲存在核心產品資料夾中的 Config.xml 檔案 (例如，- _product_。WW) 指示安裝程式安裝該產品。 例如，下列資料夾中的 Config.xml 檔會安裝商務用 Skype：

- \\server\share\Skype15\Skype.WW \Config.xml

下表列出最常用於商務用 Skype 安裝的 Config.xml 元素。

**Config.xml 元素**


| **元素**              | **描述**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 組態  <br/>     | 最上層元素 (必要)。 包含 Product 屬性，例如： Product = Lync (此功能會針對商務用 Skype 用戶端運作)   <br/>                                                                                                                                                          |
| OptionState  <br/>       | 指定在安裝期間如何處理特定的產品功能。 使用下列屬性可防止安裝 Business Connectivity Services，其中包含干擾 Outlook 的共用元件： <br/>  識別碼 = "LOBiMain" <br/>  State = "不存在" <br/>  子系 = "Force" <br/> |
| 顯示器  <br/>           | 安裝程式向使用者顯示的 UI 層級。一般屬性包括： <br/>  CompletionNotice= "Yes"                                                                                                                                                                                |
| 記錄  <br/>           | 安裝程式執行之記錄類型的選項。一般屬性包括： <br/>  Type = "Off"                                                                                                                                                                                       |
| 設定  <br/>           | 指定 Windows Installer 內容的值。一般屬性包括：<br/>  設定識別碼 = " *name*" (Windows Installer 屬性的名稱)   <br/>  Value = " *value*" (要指派給屬性的值)   <br/>                                                             |
| DistributionPoint  <br/> | 要執行安裝之網路安裝點的完整路徑。包括 Location 屬性：<br/>  Location = " *path*"  <br/>                                                                                                                                     |

下列範例顯示商務用 Skype 用戶端一般無訊息安裝的 Config.xml 檔案。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

您可以在使用 Config.xml 檔案執行 Office 安裝及維護工作的詳細資訊 [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 。

## <a name="to-customize-the-configxml-file"></a>自訂 Config.xml 檔案

1. 使用文字編輯器工具來開啟 Config.xml 檔案，例如 [記事本]。

2. 找到包含您要變更之元素的那幾行。

3. 以您要使用的無訊息選項來修改元素項目。 請務必移除批註定界符 " \<!--" and "--\> "。 例如，使用下列語法：

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. 儲存 Config.xml 檔案。