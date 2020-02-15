---
title: Lync Server 2013： 部署程序的通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29e896aa89fe6fadecab3d17689d92671ffe6966
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中的通話駐留的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-25_

本節提供部署通話駐留應用程式的相關步驟的概觀。 設定通話駐留之前，您必須部署 Enterprise Edition 或 Standard Edition 與 Enterprise Voice。 通話駐留所需的元件會安裝並啟用當您部署企業語音。

### <a name="call-park-deployment-process"></a>通話駐留部署程序

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>所需群組和角色</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定軌道表中的通話駐留軌道範圍</p></td>
<td><p>使用 Lync Server Control Panel 或<strong>New-cscallparkorbit</strong> cmdlet 以通話駐留軌道表建立的軌道範圍，以及其關聯的應用程式服務主控的通話駐留應用程式。</p>
<div>

> [!NOTE]  
> 與現有的撥號對應表計劃的緊密整合，針對軌道範圍通常設定為虛擬分機區塊。 不支援將直接向內撥號 (DID) 號碼指派為通話駐留軌道表中的軌道數字。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">建立或修改通話駐留軌道範圍在 Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>設定通話駐留設定</p></td>
<td><p>使用<strong>Set-cscpsconfiguration</strong> cmdlet 進行通話駐留設定。 在最低限度下，我們建議您設定來設定使用駐留的通話逾時的後援目的地<strong>OnTimeoutURI</strong>選項。您也可以設定下列設定：</p>
<ul>
<li><p>（選用）<strong>EnableMusicOnHold</strong>可啟用或停用等候音樂。</p></li>
<li><p>（選用）若要判斷次數駐留的通話週期回來接聽電話之前轉接至後援統一資源識別項 (URI) <strong>MaxCallPickupAttempts</strong> 。</p></li>
<li><p>（選用）<strong>CallPickupTimeoutThreshold</strong>決定駐留通話回接聽來電的電話之前經過的時間量。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中設定通話駐留設定</a></p></td>
</tr>
<tr class="odd">
<td><p>（選用） 自訂等候音樂</p></td>
<td><p>若要自訂及上傳音訊檔案，如果您不想要使用預設的等候音樂上保留使用<strong>Set-cscallparkservicemusiconholdfile</strong> cmdlet。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">自訂通話駐留等候音樂 Lync Server 2013 中</a></p></td>
</tr>
<tr class="even">
<td><p>設定語音原則，為使用者啟用通話駐留</p></td>
<td><p>使用 Lync Server Control Panel 或<strong>Set-csvoicepolicy</strong> cmdlet 搭配<strong>EnableCallPark</strong>選項來啟用通話駐留的語音原則中的使用者。</p>
<div>

> [!NOTE]  
> 根據預設，通話駐留已停用所有使用者。


</div>
<div>

> [!NOTE]  
> 如果您有多個語音原則，請確定每個語音原則，而不只是預設的原則設定 EnableCallPark 屬性。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">啟用 Lync Server 2013 中的使用者的通話駐留</a></p></td>
</tr>
<tr class="odd">
<td><p>確認通話駐留的正規化規則</p></td>
<td><p>通話駐留軌道必須不會被正規化。 確認的正規化規則不包含任何的軌道範圍。 如有必要，建立額外的正規化規則，以避免軌道要正規化。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">確認 Lync Server 2013 中的通話駐留的正規化規則</a></p></td>
</tr>
<tr class="even">
<td><p>確認通話駐留部署</p></td>
<td><p>測試駐留並擷取通話，請確定您的設定如預期般運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">（選用）確認 Lync Server 2013 中的通話駐留部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

