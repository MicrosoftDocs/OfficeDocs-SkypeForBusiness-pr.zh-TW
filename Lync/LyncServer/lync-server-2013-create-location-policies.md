---
title: Lync Server 2013：建立位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c10244bb3a70f7218dc3967e7f4f134048024f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a>在 Lync Server 2013 中建立位置原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

Lync Server 在用戶端註冊期間，使用位置原則來啟用 E9-1-1 的 Lync 用戶端。 位置原則包含定義 E9-1-1 將如何實現的設定。

您可以編輯全域位置原則，並建立新的標記位置原則。 當用戶端不位於關聯位置原則的子網中，或用戶端尚未直接指派位置原則時，用戶端會取得全域原則。 已將標記的原則指派給子網或使用者。

若要建立位置原則，您必須使用一個帳戶，該帳戶是 RTCUniversalServerAdmins 群組的成員，或是 CsVoiceAdministrator 系統管理角色的成員，或是具有同等的管理員權利和許可權。

如需位置原則的完整說明，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。 此程式中的 Cmdlet 使用使用下列值定義的位置原則：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>滿足</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>免責聲明</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>您的公司原則需要您設定位置。 如果您沒有設定位置，緊急服務將無法在緊急情況下找不到您。 請設定位置。</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>虛假</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>twoway</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


如需使用位置原則的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - 授與 CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>建立位置原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。
    
    <div>
    

    > [!NOTE]  
    > 如果<STRONG>PstnUsage</STRONG>的設定尚不在 PstnUsages 的全域清單中，CsLocationPolicy 將會失敗。

    
    </div>

2.  或者，您也可以執行下列 Cmdlet 來編輯全域位置原則：
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  執行下列動作來建立標籤位置原則。
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  執行下列 Cmdlet，將步驟3中建立的標籤位置原則套用至使用者原則。
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

