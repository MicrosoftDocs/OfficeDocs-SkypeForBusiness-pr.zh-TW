---
title: Lync Server 2013： Lync 2013 的新增和變更設定
description: Lync Server 2013： Lync 2013 的新增和變更設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf744e1bae774904733390ec624be523ad32bc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561389"
---
# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 的新增及變更的設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-12-05_

本主題討論與直接與用戶端管理相關之 Lync Server 管理命令介面 Cmdlet 的變更。 Lync Server 2013 引進數個新參數，並 deprecates 可透過其他方式設定之功能的參數。

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
<th>新增</th>
<th>Lync Server 管理命令介面 Cmdlet</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>設為 True 時，會在 Lync 啟用軟體追蹤;設為 False 時，軟體追蹤將會停用。 軟體追蹤包含保留程式所進行之所有事項的詳細記錄 (包括追蹤 API 呼叫)。 追蹤功能主要適用于開發人員和應用程式支援人員。此設定相當於 [通訊伺服器 2007 R2 群組原則] 設定 [ &quot; 開啟 Communicator 追蹤]。 &quot; 設定如下：</p>
<ul>
<li><p>Off = 停用追蹤，使用者無法變更此設定。</p></li>
<li><p>淺色 = 執行最小追蹤，使用者無法變更此設定。</p></li>
<li><p>On = 執行詳細追蹤，使用者無法變更此設定。</p></li>
</ul>
<p>依預設，TracingLevel 會設為 null 值。 這表示執行最小追蹤，但使用者可以啟用或停用這種最小追蹤。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>設為 True 時 ($True) 允許音訊和影片的資料流程與其他網路流量分開，這樣就能讓用戶端裝置在本機進行音訊和影片的編碼和解碼。 與裝置遠端處理或轉碼器壓縮等類似的技術相較，媒體重新導向通常會使頻寬使用較低、伺服器擴充性較高，且使用者經驗較佳。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>設為 True 時，會將所有 Lync 會議視為 &quot; 大型會議。 &quot; 使用大型會議時，除了預設傳輸的會議名單大小之外，也會限制傳送給參與者的通知數目。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>設為 True 時 ($True) 使用者將無法將批註新增至會議中所用 PowerPoint 的投影片。 不過 (取決於 AllowAnnotations 屬性的值) ，使用者仍可存取其他的白板功能。 預設值為 False，表示允許使用 PowerPoint 批註。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>設為 True 時 (預設值) 會自動更新連結至會議的任何開啟 OneNote 筆記本的資訊，例如會議參與者的資訊，以及在會議期間共用之內容的詳細資料。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>與其他新的 CsMeetingConfiguration 參數一起使用，以自訂 Lync 2013 之線上會議增益集所產生的會議邀請。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將組織的標誌新增至所有由 Lync 2013 之線上會議增益集所產生的所有邀請。 您可以指定 GIF 或 JPG 圖像的 URL。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將您組織的說明或支援 URL 新增至 Lync 2013 之線上會議增益集所產生的所有邀請。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>針對 Lync 2013 的線上會議增益集所產生的所有邀請，新增法律文字或免責聲明文字。 您可以指定文字位置的 URL。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>會將自訂的頁尾新增至由 Lync 2013 之線上會議增益集所產生的所有邀請。 您可以指定自訂頁腳文字位置的 URL。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>已被取代的用戶端管理參數


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
<td><p>此參數已被取代，無法搭配 Lync Server 2013 使用。 與 EnableEnterpriseCustomizedHelp 搭配使用時，此參數會讓組織指定 URL，這樣當使用者按一下 Lync 中的 [說明] 功能表時，就會顯示自訂的 [說明]。</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數已被取代，無法搭配 Lync Server 2013 使用。 與 CustomizedHelpUrl 搭配使用時，此參數會讓組織顯示自訂的 [說明]。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>已在 Lync Server 2013 中移除 Set-CSClientPolicy Cmdlet 的 EnableSQMData 參數。 相反地，您可以使用「軟體品質管制」的共用群組原則設定來 (SQM) 資料，以判斷「Lync 用戶端一般選項」頁面中的「客戶經驗改進」選項的使用者介面：</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>值：</p>
<p>1 = 顯示並選取此核取方塊 (使用者可以清除核取方塊) </p>
<p>0 = 關閉並停用此核取方塊 (使用者無法覆寫) </p>
<p>Null = 此值是由 Office 安裝程式所決定，而且會顯示一個核取方塊，讓使用者將其設定為選擇</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數已被移除。 相反地，當您部署 Lync Server 2013 併發行拓撲時，預設會為所有使用者啟用整合連絡人存放區。 這表示，所有使用者的連絡人都會保留在 Exchange 中，且可用於 Lync、Outlook 和 Outlook Web Access。 您可以使用 Set-CsUserServicesPolicy Cmdlet 來自訂哪些使用者擁有整合的連絡人存放區。 您可以依租使用者或個別個人或個別群組的方式啟用使用者。 如需詳細資訊，請參閱 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中啟用整合連絡人存放區的使用者</a>。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync 2013 不會使用此參數。 在舊版本中，此參數指定用戶端從 Exchange 公用資料夾中檢索 MAPI 資料的頻率</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數在 Lync 2013 中已被取代。</p></td>
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

