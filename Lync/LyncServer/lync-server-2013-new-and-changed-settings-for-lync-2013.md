---
title: Lync Server 2013： Lync 2013 的新增及變更的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 的新增及變更的設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-05_

本主題討論與用戶端管理直接相關的 Lync Server 管理命令介面 Cmdlet 變更。 Lync Server 2013 會引入數個新參數，並 deprecates 可透過其他方式設定的功能的參數。

<div>

## <a name="new-client-management-parameters"></a>新的用戶端管理參數


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>新增功能</th>
<th>Lync Server 管理命令介面 Cmdlet</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>當設定為 True 時，會在 Lync 啟用軟體追蹤;當設為 False 時，軟體追蹤將停用。 軟體追蹤涉及對程式所執行的所有專案（包括追蹤 API 呼叫）進行詳細記錄。 追蹤功能對開發人員和應用程式支援人員而言是很有用的。這個設定相當於通訊伺服器 2007 R2 群組原則設定&quot;開啟 Communicator 追蹤功能。&quot;這些設定如下所示：</p>
<ul>
<li><p>關閉 = 已停用追蹤，且使用者無法變更此設定。</p></li>
<li><p>Light = 執行最小追蹤，使用者無法變更此設定。</p></li>
<li><p>開啟 = 進行詳細追蹤，使用者無法變更此設定。</p></li>
</ul>
<p>根據預設，TracingLevel 會設定為 null 值。 這表示會執行最少的追蹤，但使用者可以啟用或停用這種最小追蹤。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>當設定為 True （$True）時，會讓音訊和影片資料流程與其他網路流量分開，進而讓用戶端裝置在本機進行音訊與視頻解碼及解碼。 媒體重新導向通常會產生較低的頻寬使用量、較高的伺服器可伸縮性，以及與類似裝置（例如裝置遠端處理或編解碼器壓縮）相比更加最佳的使用者體驗。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>當設定為 True 時，所有 Lync 會議都會被&quot;視為大型會議。&quot;使用大型會議時，除了預設傳送的會議名單大小之外，還會針對傳送給參與者的通知數量加上限制。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>當設定為 True （$True）時，使用者將無法在會議中使用 PowerPoint 投影片上新增批註。 不過（視 AllowAnnotations 屬性的值而定），使用者仍可存取其他 whiteboarding 功能。 預設值為 False，表示允許使用 PowerPoint 標注。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>當設定為 True （預設值）時，連結至會議的任何開啟的 OneNote 筆記本都會自動更新，其中包含會議參與者的相關資訊，以及在會議期間共用之內容的詳細資料。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>與其他新的 CsMeetingConfiguration 參數搭配使用，來自訂 Lync 2013 的線上會議增益集所產生的會議邀請。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將貴組織的標誌新增至由 Lync 2013 的線上會議增益集所產生的所有邀請。 您可以指定 GIF 或 JPG 影像的 URL。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將貴組織的說明或支援 URL 新增到由 Lync 2013 的線上會議增益集所產生的所有邀請。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>在 Lync 2013 的線上會議增益集所產生的所有邀請中，新增法律文字或免責聲明文字。 您可以指定文字位置的 URL。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將自訂頁尾新增至由 Lync 2013 的線上會議增益集所產生的所有邀請。 您可以指定自訂頁尾文字位置的 URL。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>過時的用戶端管理參數


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>參數</th>
<th>Lync Server 管理命令介面 Cmdlet</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數已棄用，可與 Lync Server 2013 搭配使用。 與 EnableEnterpriseCustomizedHelp 搭配使用時，此參數會讓組織指定 URL，以便在使用者按一下 Lync 中的 [說明] 功能表時，自訂的 [說明] 會顯示。</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數已棄用，可與 Lync Server 2013 搭配使用。 與 CustomizedHelpUrl 搭配使用時，此參數可讓組織顯示自訂的說明。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>已在 Lync Server 2013 中移除 Set CSClientPolicy Cmdlet 的 EnableSQMData 參數。 相反地，您可以使用軟體品質管制（SQM）資料的共用群組原則設定來決定 [Lync 用戶端一般選項] 頁面中的 [客戶經驗改進] 選項的使用者介面：</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>相對值</p>
<p>1 = 顯示並選取核取方塊（使用者可以清除核取方塊）</p>
<p>0 = 關閉並停用核取方塊（使用者無法覆寫）</p>
<p>Null = 此值是由 Office 設定決定，且會顯示使用者設定的核取方塊，讓使用者選擇</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數已移除。 相反地，當您部署 Lync Server 2013 併發布拓撲時，預設會啟用所有使用者的「整合連絡人存放區」。 這表示所有使用者的連絡人都會保留在 Exchange 中，且可在 Lync、Outlook 和 Outlook Web Access 中取得。 您可以使用 CsUserServicesPolicy Cmdlet 來自訂哪些使用者可以使用 [整合] 連絡人存放區。 您可以將使用者全域性、依網站、由租使用者，或由個人或一組人員來啟用。 如需詳細資訊，請參閱<a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中為整合連絡人存放區啟用使用者</a>。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync 2013 不會使用這個參數。 在前一個版本中，此參數指定用戶端從 Exchange 公用資料夾中檢索到 MAPI 資料的頻率</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>在 Lync 2013 中已棄用此參數。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

