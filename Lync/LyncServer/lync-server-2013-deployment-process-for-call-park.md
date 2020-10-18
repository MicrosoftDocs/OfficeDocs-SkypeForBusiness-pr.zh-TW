---
title: Lync Server 2013：通話駐留的部署程式
description: Lync Server 2013：通話駐留的部署程式。
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
ms.openlocfilehash: 149252d39ba3fc0c552900c87e453c60e1651a08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575709"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

本節概述部署通話駐留應用程式所需的步驟。 您必須先部署 Enterprise Edition 或 Standard Edition 搭配 Enterprise Voice，才能設定通話駐留。 當您部署企業語音時，會安裝並啟用通話駐留所需的元件。

### <a name="call-park-deployment-process"></a>通話駐留部署程式

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
<td><p>在軌道表格中設定通話駐留軌道範圍</p></td>
<td><p>使用 Lync Server 控制台或 <strong>New-CSCallParkOrbit</strong> Cmdlet 來建立通話駐留軌道表格中的軌道範圍，並將其關聯至主控通話駐留應用程式的應用程式服務。</p>
<div>

> [!NOTE]  
> 為了與現有的撥號對應表進行無縫整合，軌道範圍通常會設定為虛擬擴充區塊。 指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</a></p></td>
</tr>
<tr class="even">
<td><p>設定通話駐留設定</p></td>
<td><p>使用 <strong>Set-CsCpsConfiguration</strong> Cmdlet 來設定通話駐留設定。 建議您至少將 <strong>OnTimeoutURI</strong> 選項設定為設定要在寄存通話超時時使用的回退目的地。您也可以設定下列設定：</p>
<ul>
<li><p> (選用) <strong>EnableMusicOnHold</strong> 啟用或停用等候的音樂。</p></li>
<li><p> (選用) <strong>MaxCallPickupAttempts</strong> 決定寄存來電在將來電轉送至回復的備用資源識別元 (URI) 之前所用的次數。</p></li>
<li><p> (選用) <strong>CallPickupTimeoutThreshold</strong> 可決定通話之後所經過的時間長度，超過此時間之後，它會在接聽來電的電話之前所經過的時間。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中設定通話駐留設定</a></p></td>
</tr>
<tr class="odd">
<td><p>（選用）自訂等候音樂</p></td>
<td><p>如果您不想要使用預設的等候音樂，請使用 <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> Cmdlet 自訂和上傳音訊檔案。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自訂通話駐留的等候音樂</a></p></td>
</tr>
<tr class="even">
<td><p>設定語音原則為使用者啟用通話駐留</p></td>
<td><p>使用 Lync Server 控制台或具有<strong>EnableCallPark</strong>選項的<strong>Set-CSVoicePolicy</strong> Cmdlet，為語音原則中的使用者啟用通話駐留。</p>
<div>

> [!NOTE]  
> 預設會停用所有使用者的通話駐留。


</div>
<div>

> [!NOTE]  
> 如果您有多個語音原則，請確定針對每個語音原則設定 EnableCallPark 屬性，而不只是針對預設原則。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中為使用者啟用通話駐留</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證通話駐留的正規化規則</p></td>
<td><p>通話駐留軌道不得正規化。 請確認您的正規化規則不包含任何軌道範圍。 如有必要，請建立其他正規化規則，以防止軌道正規化。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中驗證通話駐留的正規化規則</a></p></td>
</tr>
<tr class="even">
<td><p>驗證通話駐留部署</p></td>
<td><p>測試停車場和取回通話，以確保您的設定如預期般運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md"> (選用) 在 Lync Server 2013 中驗證通話駐留部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

