---
title: Lync Server 2013：新增命令至 Lync 功能表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 738f745d4f91458b95e95e5cc5770c34ed4e8c88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521350"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>將命令新增至 Lync Server 2013 中的 Lync 功能表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-11_

您可以將自訂命令新增至 Lync 2013 功能表，並將目前使用者及選取之連絡人的 SIP 統一資源識別項傳遞給該自訂命令啟動的應用程式 (URI) 。

您新增的自訂命令可以出現在下列一或多個功能表上：

  - [工具] 功能表，在 Lync 主視窗中的功能表列上

  - 連絡人清單中連絡人的快顯功能表

  - [更多選項] 功能表的 [交談] 視窗

  - 在交談視窗參與者清單中列出之人員的快顯功能表

  - 連絡人卡片中的 [選項] 功能表

您可以為兩種類型的應用程式定義自訂命令：執行下列其中一項的應用程式：

  - 僅適用于目前的使用者，並在本機電腦上啟動。

  - 包含其他使用者（例如線上共同作業計畫），且必須在每一位使用者的電腦上啟動。

您可以透過下列方式呼叫自訂命令：

  - 選取一或多個使用者，然後選擇自訂命令。

  - 啟動兩方或多方交談，然後選擇自訂命令。

<div>

## <a name="to-add-a-custom-command"></a>若要新增自訂命令

使用下表中的登錄設定，將命令新增至功能表。 這些專案會放在登錄的下列其中一個位置：

  - 針對32位作業系統： HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式

  - 針對64位作業系統： HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ Wow6432Node \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ 應用程式

### <a name="custom-command-registry-entries"></a>自訂命令登錄專案

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>類型</th>
<th>Data (資料)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>姓名</p></td>
<td><p>REG_SZ</p></td>
<td><p>顯示在功能表上的應用程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 可執行檔 (預設) </p>
<div>

> [!NOTE]  
> 需要 ApplicationInstallPath。


</div>
<p>1 = 通訊協定</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>可執行檔的完整路徑。</p>
<div>

> [!NOTE]  
> 如果 ApplicationType 為 0 (可執行檔) 則必須指定。


</div></td>
</tr>
<tr class="even">
<td><p>路徑</p></td>
<td><p>REG_SZ</p></td>
<td><p>要與任何參數一起啟動的完整路徑，包括預設參數<em>% user 識別碼% user 識別碼</em>% <em>。</em></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本機工作階段。在本機電腦上啟動應用程式。</p>
<p>1 = 兩方工作階段 (預設)。 Lync 2013 會在本機啟動應用程式，然後將桌面通知傳送給另一個使用者。 另一部使用者按一下通知，以在其電腦上啟動應用程式。</p>
<p>2 = 多方工作階段。 Lync 2013 會在本機啟動應用程式，然後將桌面通知傳送給其他使用者。 另一部使用者按一下通知，以在其電腦上啟動指定的應用程式。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>會出現這個命令的功能表清單，以分號分隔。 可能的值有：</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</p></td>
</tr>
</tbody>
</table>


例如，下列登錄編輯程式 (。REG) file 顯示在 [交談] 視窗中，將 Contoso Sales Contact Manager 功能表項目新增至 [動作] 功能表的結果：

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>存取自訂命令

若要在新增自訂命令之後存取它，請根據您定義的 ExtensibleMenu 值，執行下列其中一項操作：

  - **MainWindowActions**    在 Lync 主視窗中，按一下 [**工具**]，然後按一下您的自訂命令。

  - **MainWindowRightClick**    在 Lync 主視窗中，以滑鼠右鍵按一下連絡人，然後按一下您的自訂命令。

  - **ConversationWindowActions**    在 [交談] 視窗中，按一下 [**其他選項**] 圖示，然後按一下您的自訂命令。

  - **ConversationWindowRightClick**    在 [交談] 視窗中，以滑鼠右鍵按一下連絡人名稱，然後按一下您的自訂命令。

</div>

</div>

<span> </span>

</div>

</div>

</div>

