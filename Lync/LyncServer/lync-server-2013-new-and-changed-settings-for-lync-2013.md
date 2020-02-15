---
title: Lync 2013 的 Lync Server 2013： 新增及變更設定
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
ms.openlocfilehash: 45282476beac35df7248c4ef6bd04c6642a0f1e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 的新增及變更設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-12-05_

本主題討論變更至與用戶端管理直接相關的 Lync Server 管理命令介面指令程式。 Lync Server 2013 引進數個新參數，並 deprecates 參數可以透過其他方式進行設定的功能。

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
<th>Lync Server 管理命令介面指令程式</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>當您將會設為 True，軟體追蹤啟用在 Lync;當設為 False，軟體追蹤將會停用。 軟體追蹤包含保留程式所進行之所有事項的詳細記錄 (包括追蹤 API 呼叫)。 追蹤是大部分有用的開發人員和應用程式的支援人員。此設定相當於 [Communications Server 2007 R2 群組原則設定&quot;開啟 Communicator 追蹤。&quot; ，如下所示的設定包括：</p>
<ul>
<li><p>關 = 停用追蹤，使用者無法變更此設定。</p></li>
<li><p>輕 = 執行最基本的追蹤是，且使用者無法變更此設定。</p></li>
<li><p>開 = Verbose 追蹤已執行，且使用者無法變更此設定。</p></li>
</ul>
<p>根據預設 TracingLevel 設為 null 值。 這表示會執行最基本的追蹤，但使用者可以啟用或停用這個最基本的追蹤。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>當設為 True ($True) 可讓與其他的網路流量，依序分開的音訊和視訊資料流時，這可讓用戶端裝置進行編碼和解碼音訊及視訊在本機上。 與裝置遠端處理或轉碼器壓縮等類似的技術相較，媒體重新導向通常會使頻寬使用較低、伺服器擴充性較高，且使用者經驗較佳。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>設為 True 時，所有 Lync Meeting 都視為&quot;大型會議。&quot;大型會議，以限制置於此外預設傳輸的會議名冊大小傳送給參與者的通知數目。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>當設為 True ($True) 使用者將無法將註解新增至 PowerPoint 投影片在會議中使用。 不過，（根據 AllowAnnotations 屬性的值），使用者仍會有其他白板功能的存取權。 預設值為 False，這表示可允許 PowerPoint 註釋。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>當設為 True （預設值） 在任何開啟連結到會議的 OneNote 筆記本會自動更新會議參與者和詳細資料等在會議期間共用的內容相關的資訊。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>與其他新 CsMeetingConfiguration 參數一起使用自訂的線上會議增益集 Lync 2013 所產生的會議邀請。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將貴組織的商標新增至產生的線上會議增益集 Lync 2013 的所有邀請。 您指定 GIF 或 JPG 影像 URL。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將貴組織的說明或支援 URL 新增至產生的線上會議增益集 Lync 2013 的所有邀請。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將法律或免責聲明文字新增至產生的線上會議增益集 Lync 2013 的所有邀請。 您指定文字的位置的 URL。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>將自訂的頁尾新增至產生的線上會議增益集 Lync 2013 的所有邀請。 您指定的自訂頁尾文字的位置的 URL。</p></td>
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
<th>Lync Server 管理命令介面指令程式</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>搭配 Lync Server 2013 已淘汰此參數。 中 enableenterprisecustomizedhelp 設搭配使用時，此參數會啟用組織，以指定的 URL，這樣當使用者按下 Lync 中的 [說明] 功能表，會顯示自訂的說明。</p></td>
</tr>
<tr class="even">
<td><p>Enableenterprisecustomizedhelp 設</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>搭配 Lync Server 2013 已淘汰此參數。 中 CustomizedHelpUrl 搭配使用時，此參數會啟用組織若要顯示自訂的說明。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync Server 2013 中已移除 Set-csclientpolicy cmdlet 的 EnableSQMData 參數。 相反地，您可以使用軟體品質管理 (SQM) 資料共用的群組原則的設定來決定在 Lync 用戶端一般選項] 頁面的 [客戶經驗改進] 選項的使用者介面：</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>值：</p>
<p>1 = 顯示並選取核取方塊 （使用者可以清除核取方塊）</p>
<p>0 = 關閉並停用] 核取方塊 （使用者無法覆寫）</p>
<p>Null = 值取決於 Office 安裝程式，並且] 核取方塊會顯示使用者設為他們選擇</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此參數已被移除。 相反地，當您部署 Lync Server 2013，並發行拓撲，整合連絡人存放區預設會啟用所有使用者。 這表示所有使用者的連絡人會保留在 Exchange 和 Lync、 Outlook 和 Outlook Web Access 中提供。 您可用於自訂哪些使用者具有整合連絡人存放區提供 Set-csuserservicespolicy cmdlet。 您可以啟用全域、 網站、 租用戶，或藉由個人或群組的個人的使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-enable-users-for-unified-contact-store.md">啟用使用者的 Lync Server 2013 中整合連絡人存放區</a>。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync 2013 不使用此參數。 在先前版本中，此參數會指定用戶端從 Exchange 公用資料夾擷取 MAPI 資料的頻率</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync 2013 中，此參數已被取代。</p></td>
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

