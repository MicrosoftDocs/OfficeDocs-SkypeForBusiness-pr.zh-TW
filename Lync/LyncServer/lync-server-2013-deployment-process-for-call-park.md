---
title: Lync Server 2013：通話寄存的部署程式
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
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留的部署程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-25_

本節概要說明部署通話駐留應用程式所涉及的步驟。 您必須先使用企業語音部署企業版或標準版，才能設定通話駐留。 當您部署企業語音時，系統會安裝並啟用通話駐留所需的元件。

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
<th>分</th>
<th>步驟</th>
<th>必要的群組和角色</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設定 [軌道] 表格中的 [通話駐留軌道] 範圍</p></td>
<td><p>使用 Lync Server [控制台] 或<strong>新的 CSCallParkOrbit</strong> Cmdlet，在 [通話駐留軌道] 表格中建立軌道範圍，並將它們與託管通話駐留應用程式的應用程式服務建立關聯。</p>
<div>

> [!NOTE]  
> 若要與現有的撥號方案進行無縫整合，軌道範圍通常是設定為虛擬延伸的區塊。 在 [通話駐留軌道] 表格中，將直向內撥（所做的）號碼指派為軌道編號，不受支援。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中建立或修改通話駐留軌道的範圍</a></p></td>
</tr>
<tr class="even">
<td><p>設定通話駐留設定</p></td>
<td><p>使用<strong>CsCpsConfiguration</strong> Cmdlet 來設定 [通話駐留] 設定。 我們建議您至少設定<strong>OnTimeoutURI</strong>選項，以設定在寄存通話超時時要使用的備用目的地。您也可以設定下列設定：</p>
<ul>
<li><p>可選<strong>EnableMusicOnHold</strong>以啟用或停用音樂保留。</p></li>
<li><p>可選<strong>MaxCallPickupAttempts</strong> ，決定在將來電轉接到回退統一資源識別項（URI）之前，寄存通話響鈴回到接聽電話的次數。</p></li>
<li><p>可選<strong>CallPickupTimeoutThreshold</strong> ，決定通話在撥出到接聽通話的電話之前所經過的時間長度。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中設定通話駐留設定</a></p></td>
</tr>
<tr class="odd">
<td><p>或者，您也可以自訂 [等候音樂]</p></td>
<td><p>如果您不想使用預設的音樂保留，請使用<strong>CsCallParkServiceMusicOnHoldFile</strong> Cmdlet 來自訂及上傳音訊檔案。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自訂通話寄存音樂暫停</a></p></td>
</tr>
<tr class="even">
<td><p>設定語音原則，為使用者啟用通話駐留</p></td>
<td><p>使用 Lync Server [控制台] 或<strong>CSVoicePolicy</strong> Cmdlet 與<strong>EnableCallPark</strong>選項，在語音原則中為使用者啟用通話駐留。</p>
<div>

> [!NOTE]  
> 根據預設，會停用所有使用者的 [通話駐留]。


</div>
<div>

> [!NOTE]  
> 如果您有多個語音原則，請務必針對每個語音原則設定 EnableCallPark 屬性，而不只是針對預設原則。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中為使用者啟用通話駐留</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證通話駐留的正規化規則</p></td>
<td><p>通話駐留軌道式一定不能正常化。 確認您的正常化規則不包含任何您的軌道範圍。 如有需要，請建立其他正常化規則，以避免讓軌道式成為正常化的。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中驗證通話寄存的正常化規則</a></p></td>
</tr>
<tr class="even">
<td><p>確認您的電話寄存部署</p></td>
<td><p>測試停用和檢索通話，以確保您的設定如預期的那樣正常運作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">可選在 Lync Server 2013 中確認通話駐留部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

