---
title: 在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml 檔案來指定其他安裝指示。
ms.openlocfilehash: a935e3623e99324eb24caef4e7e232d2311c5cfb
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768646"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>在商務用 Skype 用戶端中使用 Config.xml 執行安裝工作

**摘要：** 如何使用 Config.xml 檔案來指定其他安裝指示。

雖然 Office 自訂工具（OCT）是自訂安裝的主要工具，但系統管理員可以使用 Config.xml 檔案來指定不在 OCT 中提供的其他安裝指示。 下列自訂功能只能使用 Config.xml 檔案來進行：

- 指定網路安裝點的路徑。

- 選取要安裝的產品。

- 設定記錄，以及安裝程式自訂檔案和軟體更新的位置。

- 指定安裝選項，例如 [使用者名稱]。

- 將本機安裝來源（.LIS）複製到使用者的電腦，但不安裝 Office。

- 新增或移除安裝的語言。

建議您使用 Config.xml 檔案來設定商務用 Skype 無訊息安裝。 

根據預設，儲存在核心產品資料夾中的 Config.xml 檔案（例如，[_產品_]）。WW）指示安裝程式安裝該產品。 例如，下列資料夾中的 Config.xml 檔案會安裝商務用 Skype：

- \\server\share\Skype15\Skype.WW \Config.xml

下表列出最常用於商務用 Skype 安裝的 Config .xml 元素。

**Config .xml 元素**


| **元件**              | **說明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration  <br/>     | 高層元素（必要）。 包含 Product 屬性，例如： Product = Lync （這適用于商務用 Skype 用戶端）  <br/>                                                                                                                                                          |
| OptionState  <br/>       | 指定安裝期間特定產品功能的處理方式。 使用下列屬性來避免安裝 Business Connectivity Service，其中包含會干擾 Outlook 的共用元件： <br/>  識別碼 = "LOBiMain" <br/>  State = "不存在" <br/>  子級 = "Force" <br/> |
| 顯示幕  <br/>           | 安裝程式顯示給使用者的 UI 層級。 一般屬性包括下列各項： <br/>  CompletionNotice = "Yes"                                                                                                                                                                                |
| 記錄  <br/>           | 安裝程式所執行之記錄類型的選項。 一般屬性包括下列各項： <br/>  輸入 = "Off"                                                                                                                                                                                       |
| 正在  <br/>           | 指定 Windows 安裝程式屬性的值。 一般屬性包括下列各項： <br/>  設定識別碼 = " *name*" （Windows Installer 屬性的名稱）  <br/>  Value = " *value*" （要指派給屬性的值）  <br/>                                                             |
| DistributionPoint  <br/> | 要執行安裝的網路安裝點的完整路徑。 包括 Location 屬性： <br/>  位置 = " *path*"  <br/>                                                                                                                                     |

下列範例顯示商務用 Skype 用戶端的典型無訊息安裝的 Config.xml 檔案。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

有關使用 Config.xml 檔案來執行 Office 安裝與維護工作的詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)。

## <a name="to-customize-the-configxml-file"></a>自訂 Config.xml 檔案

1. 使用文字編輯器工具（例如記事本）來開啟 Config.xml 檔案。

2. 找出包含您要變更之元素的線條。

3. 使用您要使用的緘默選項來修改元素專案。 請務必移除批註分隔符號 "\<!--" 和 "--\>"。 例如，使用下列語法：

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. 儲存 Config.xml 檔案。


