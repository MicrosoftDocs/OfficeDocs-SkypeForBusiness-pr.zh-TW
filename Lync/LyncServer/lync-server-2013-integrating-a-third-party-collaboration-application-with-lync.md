---
title: 使用 Lync 整合的協力廠商共同作業應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>整合的協力廠商共同作業應用程式與 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-20 個_

您可以新增至登錄的應用程式的相關資訊，與任何協力廠商線上共同作業應用程式整合 Lync 2013。 您可以使用 Lync 2013 啟動裝載於內部伺服器、 網際網路為基礎的服務，或兩者上的資料會議工作階段。 您可以從 [連絡人清單] 或從現有的立即訊息、語音或視訊工作階段，啟動共同作業或資料會議工作階段。 Lync 2013 僅作為啟動應用程式的工具。 開始在線上共同作業工作階段之後，保持使用中任何現有的 Lync 2013 交談。

下列各節說明如何將 Lync 2013 整合與網際網路與伺服器共同作業應用程式。

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>整合網際網路共同作業應用程式與 Lync 2013

基本上，與協力廠商共同作業應用程式整合相關的步驟如下：

1.  應用程式的相關資訊會新增到登錄中。

2.  組合管理登入 Lync 2013，並選取資料的共用與共同作業的連絡人。 或者，召集人可能已經在交談中，並決定新增資料會議。

3.  Lync 2013 會讀取登錄、 啟動共同作業應用程式，然後傳送自訂 SIP 訊息 — appINVITE — 給選取的參與者。

4.  參與者會接受邀請，並在每個人的電腦上啟動共同作業應用程式。 Lync 2013 會使用登錄來判斷哪些共同作業應用程式使用，而且再啟動該應用程式所使用的參數包含在 appINVITE 郵件。

下表說明與 Lync 2013 整合網際網路共同作業應用程式所需的登錄項目。 這些項目會放在登錄中的下列位置：

  - HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\參數

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>網際網路共同作業應用程式的登錄項目

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
<td><p>名稱</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lync 2013 功能表應用程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>16 像素 x 16 像素圖示 (BMP 或 PNG) 的路徑。</p></td>
</tr>
<tr class="odd">
<td><p>路徑</p></td>
<td><p>REG_SZ</p></td>
<td><p>啟動線上共同作業應用程式的參與者路徑。</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>啟動線上共同作業應用程式的召集人路徑。 這個路徑可以包含一或多個自訂參數，做為 Parameters 子機碼中定義的參數。 例如，<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本機工作階段。在本機電腦上啟動應用程式。</p>
<p>1 = 兩方工作階段 (預設)。 Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者。 另一位使用者按一下通知並在他們的電腦上啟動指定的應用程式。</p>
<p>2 = 多方工作階段。 Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者，提示使用者在自己的電腦上啟動指定的應用程式。</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>會出現這個命令的功能表清單 (以分號分隔)。可能的值有：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</p></td>
</tr>
</tbody>
</table>


下表說明參數的登錄項目。 這些項目是在 HKEY\_目前\_使用者\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\參數。

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>網際網路共同作業應用程式的登錄項目

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
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>語彙基元化格式中使用 (<code>%Parm1%</code>) 將使用者特定的值新增到 OriginatorPath 登錄機碼。</p></td>
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


下列範例會登錄設定與 Lync 2013 整合 ADatum Collaboration Client:

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>整合伺服器共同作業應用程式與 Lync 2013

若要新增命令以啟動 Lync 2013 內從伺服器型的共同作業應用程式的設定很類似所描述的前一個] 區段中，整合網際網路型的共同作業應用程式與 Lync 2013。 不過，不需要 OriginatorPath，而且有些值已經變更。 登錄項目會放在下列位置：

  - HKEY\_本機\_機器\\軟體\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\參數

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>伺服器共同作業應用程式的登錄項目

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
<td><p>名稱</p></td>
<td><p>REG_SZ</p></td>
<td><p>顯示在功能表上的應用程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>值 = 1。 將應用程式類型設定成通訊協定。 其他可能的值則在這個情況不適用。 如果不存在，ApplicationType 設為 0 （可執行檔）。</p></td>
</tr>
<tr class="odd">
<td><p>路徑</p></td>
<td><p>REG_SZ</p></td>
<td><p>用來啟動共同作業應用程式的通訊協定。 Live Meeting 2007，路徑的值設為<code>meet:%conf-uri%</code>。</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 本機工作階段。在本機電腦上啟動應用程式。</p>
<p>1 = 兩方工作階段 (預設)。 Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者。 另一位使用者按一下通知並在他們的電腦上啟動指定的應用程式。</p>
<p>2 = 多方工作階段。 Lync 2013 啟動在本機上，在應用程式，然後將系統通知傳送給其他使用者，提示使用者在其電腦上啟動指定的應用程式。</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = 伺服器的類型。</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>此命令將會出現的位置，功能表清單以分號分隔。 可能的值有：</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>如果沒有定義 ExtensibleMenu ，會使用 MainWindowRightClick 和 ConversationWindowActions 的預設值。</p></td>
</tr>
</tbody>
</table>


下列範例會啟動 ADatum Collaboration Client 從 Lync 2013 內的命令：

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

