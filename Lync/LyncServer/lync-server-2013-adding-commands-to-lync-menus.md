---
title: Lync Server 2013： 將命令新增至 Lync 功能表
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
ms.openlocfilehash: 96a0df07a44392857f4384a1285245229874cdaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>將命令新增至 Lync Server 2013 中的 Lync 功能表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-04-11_

您可以將自訂命令新增至 Lync 2013 功能表，並將 SIP 統一資源識別元 (URI) 的目前使用者] 和 [所選的連絡人傳遞至自訂命令啟動的應用程式。

您新增的自訂命令可以出現在一或多個下列功能表上：

  - [工具] 功能表上的功能表列，在 Lync 主視窗

  - 在 [連絡人] 清單中的連絡人快顯功能表

  - [更多選項] 功能表中 [交談] 視窗

  - 在 [交談] 視窗參與者清單中所列人員快顯功能表

  - [選項] 功能表中的連絡人卡片

您可以定義自訂命令以兩種類型的應用程式-應用程式，執行下列其中一項：

  - 僅適用於目前的使用者和本機電腦上啟動。

  - 包含其他使用者，例如線上共同作業的程式，且必須每位使用者的電腦上啟動。

可以透過下列方式叫用自訂命令：

  - 選取一或多個使用者，然後選擇 [自訂命令。

  - 啟動雙方或多方交談，，，然後選擇自訂命令。

<div>

## <a name="to-add-a-custom-command"></a>若要新增自訂命令

使用下表中的登錄設定，可將命令新增至功能表。 這些項目會放置在登錄的下列位置：

  - 針對 32 位元作業系統： HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用程式

  - 針對 64 位元的作業系統： HKEY\_本機\_機器\\軟體\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用程式

### <a name="custom-command-registry-entries"></a>自訂命令登錄項目

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>Type</th>
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
<td><p>0 = 可執行檔 （預設值）</p>
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
> 必須指定是否 ApplicationType 為 0 （可執行檔）。


</div></td>
</tr>
<tr class="even">
<td><p>路徑</p></td>
<td><p>REG_SZ</p></td>
<td><p>為與任何參數，包括預設參數<em>%使用者識別碼 %</em>和<em>%連絡人識別碼 %</em>一起啟動的完整路徑。</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本機工作階段。在本機電腦上啟動應用程式。</p>
<p>1 = 兩方工作階段 (預設)。 Lync 2013 啟動本機的應用程式，並再將桌面通知傳送給其他使用者。 其他使用者點選其電腦上啟動應用程式的通知。</p>
<p>2 = 多方工作階段。 Lync 2013 啟動本機的應用程式，並再將桌面通知傳送給其他使用者。 其他使用者按一下通知給他們的電腦上啟動指定的應用程式。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>此命令將會出現的位置，功能表清單以分號分隔。 可能的值有：</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</p></td>
</tr>
</tbody>
</table>


例如，下列登錄編輯程式 (。登錄） 檔案會顯示將 Contoso Sales Contact Manager 功能表項目新增至 [交談] 視窗中的 [動作] 功能表的結果：

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

## <a name="to-access-a-custom-command"></a>若要存取自訂命令

若要存取自訂命令後就當簡報加入，執行下列命令，根據您定義的 ExtensibleMenu 值其中一項：

  - **MainWindowActions**   在 Lync 主視窗中，按一下 [**工具**]，然後按一下 [您的自訂命令。

  - **MainWindowRightClick**   在 Lync 主視窗中，以滑鼠右鍵按一下連絡人，，，然後按一下 [您的自訂命令。

  - **ConversationWindowActions**   中 [交談] 視窗中，按一下 [**更多選項**] 圖示，然後按一下 [您的自訂命令。

  - **ConversationWindowRightClick**   在 [交談] 視窗中，以滑鼠右鍵按一下連絡人名稱，，，然後按一下 [您的自訂命令。

</div>

</div>

<span> </span>

</div>

</div>

</div>

