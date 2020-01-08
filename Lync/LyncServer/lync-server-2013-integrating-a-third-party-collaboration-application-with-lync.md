---
title: 將協力廠商共同作業應用程式整合到 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>將協力廠商共同作業應用程式整合到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以將 Lync 2013 與任何協力廠商線上共同作業應用程式整合，方法是將應用程式的相關資訊新增到註冊表。 您可以使用 Lync 2013 來啟動在內部公司、網際網路服務或兩者中託管的資料會議會話。 您可以從 [連絡人] 清單或從現有的立即訊息、語音或視頻會話開始，共同啟動共同作業或資料會議會話。 Lync 2013 只作為啟動應用程式的工具。 在您開始線上共同作業會話之後，任何現有的 Lync 2013 交談都會保持作用中。

下列各節說明如何將 Lync 2013 與網際網路和伺服器共同作業應用程式整合。

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>整合以網際網路為基礎的共同作業應用程式與 Lync 2013

一般來說，整合協力廠商共同作業應用程式所涉及的步驟如下：

1.  應用程式的相關資訊會新增至登錄。

2.  召集人登入 Lync 2013，然後選取 [連絡人] 以進行資料共用和共同作業。 或者，召集人可能已經在交談中，決定要新增資料會議。

3.  Lync 2013 會讀取登錄、啟動共同作業應用程式，然後將自訂 SIP 訊息（appINVITE）傳送給所選的參與者。

4.  參與者接受邀請，並在每個人員的電腦上啟動共同作業應用程式。 Lync 2013 會使用登錄來判斷要使用的共同作業應用程式，然後使用 appINVITE 訊息中所包含的參數來啟動該應用程式。

下表說明整合 Lync 2013 的網際網路式共同作業應用程式所需的登錄專案。 這些專案會放在登錄的下列位置：

  - HKEY\_本機\_電腦\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用\\程式參數

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>以網際網路為基礎的共同作業應用程式的登錄專案

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
<th>資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lync 2013 功能表的應用程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>16圖元 x 16 圖元圖示、BMP 或 PNG 的路徑。</p></td>
</tr>
<tr class="odd">
<td><p>路徑</p></td>
<td><p>REG_SZ</p></td>
<td><p>啟動線上共同作業應用程式的參與者路徑。</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>啟動線上共同作業應用程式的召集人路徑。 這個路徑可以包含一或多個在 Parameters 子機中定義的自訂參數。 例如，<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>雙倍</p></td>
<td><p>0 = 本機會話。 應用程式是在本機電腦上啟動。</p>
<p>1 = 兩方會話（預設）。 Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給其他使用者。 其他使用者按一下通知，並在他們的電腦上啟動指定的應用程式。</p>
<p>2 = 多方會話。 Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給其他使用者，以提示他們在自己的電腦上啟動指定的應用程式。</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>出現此命令的功能表清單，並以分號分隔。 可能的值包括：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果未定義 ExtensibleMenu，則會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</p></td>
</tr>
</tbody>
</table>


下表說明參數的登錄機碼目。 這些專案位於\_HKEY 目前\_的使用者\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\app\\參數。

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>以網際網路為基礎的共同作業應用程式的登錄專案

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
<th>資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>用在標記化格式<code>%Parm1%</code>（），以將使用者特定的值新增至 OriginatorPath 登錄機碼。</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>請參閱 Param1。</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>請參閱 Param1。</p></td>
</tr>
</tbody>
</table>


下列範例設定會將 ADatum 共同作業用戶端整合到 Lync 2013：

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>整合以 Lync 2013 為基礎的伺服器型共同作業應用程式

在 Lync 2013 中新增啟動伺服器式共同作業應用程式命令的設定，與前一節中所述，將網際網路式共同作業應用程式整合到 Lync 2013。 不過，不需要 OriginatorPath，而且某些值也會變更。 登錄專案會放在以下位置：

  - HKEY\_本機\_電腦\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\應用\\程式參數

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>以伺服器為基礎的共同作業應用程式的登錄專案

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
<th>資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>REG_SZ</p></td>
<td><p>出現在功能表上的應用程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>雙倍</p></td>
<td><p>值 = 1。 將應用程式類型設定為 [通訊協定]。 在此情況下，其他可能的值不適用。 如果不存在，ApplicationType 會設定為0（可執行）。</p></td>
</tr>
<tr class="odd">
<td><p>路徑</p></td>
<td><p>REG_SZ</p></td>
<td><p>用來啟動共同作業應用程式的通訊協定。 如果是 Live Meeting 2007，則 Path 的值會設定<code>meet:%conf-uri%</code>為。</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>雙倍</p></td>
<td><p>0 = 本機會話。 應用程式是在本機電腦上啟動。</p>
<p>1 = 兩方會話（預設）。 Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給其他使用者。 其他使用者按一下通知，並在他們的電腦上啟動指定的應用程式。</p>
<p>2 = 多方會話。 Lync 2013 會在本機啟動應用程式，然後將系統通知傳送給其他使用者，以提示他們在電腦上啟動指定的應用程式。</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = 伺服器的類型。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>出現此命令的功能表清單，並以分號分隔。 可能的值包括：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果未定義 ExtensibleMenu，則會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</p></td>
</tr>
</tbody>
</table>


下列範例會在 Lync 2013 中新增啟動 ADatum 共同作業用戶端的命令：

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

