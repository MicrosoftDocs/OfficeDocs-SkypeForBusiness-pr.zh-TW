---
title: 驗證組態設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>驗證組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

在您合併拓朴並執行**CsLegacyConfiguration** Cmdlet 之後，請確認您的 Office 通訊伺服器 2007 R2 原則和設定已匯入 Lync Server 2013。 下表列出您應該驗證的原則和設定。

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>遷移之後要驗證的原則和設定


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>如果您使用此工作負載：</th>
<th>驗證這些原則與設定：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>立即訊息（IM）與會議</p></td>
<td><p>目前狀態原則</p>
<p>會議原則</p></td>
</tr>
<tr class="even">
<td><p>電話撥入式會議</p></td>
<td><p>撥入存取號碼</p>
<p>撥號對應表</p></td>
</tr>
<tr class="odd">
<td><p>企業語音</p></td>
<td><p>語音原則</p>
<p>語音路由</p>
<p>撥號對應表</p>
<p>PSTN 使用量設定</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>簡單 URL</p></td>
</tr>
<tr class="odd">
<td><p>外部使用者</p></td>
<td><p>外部存取原則</p></td>
</tr>
<tr class="even">
<td><p>封存</p></td>
<td><p>存檔原則</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>驗證原則與設定

1.  在您的 Office 通訊伺服器 2007 R2 環境中，記下撥號方案的名稱（先前稱為位置設定檔）、撥入存取號碼（會議助理存取電話號碼和區域）、語音路由，以及本文中所列的原則。[前一張表格]，除了用於 Communicator Web Access 的 Url 之外。

2.  在 Lync Server 2013 前端伺服器上，開啟 [Lync Server 控制台]。

3.  若要驗證已匯入的會議原則，請在左窗格中，按一下 [**會議**]，按一下 [**會議原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有會議原則都包含在清單中。
    
    <div>
    

    > [!NOTE]  
    > 舊版 Office 通訊伺服器的<STRONG>會議</STRONG>原則現在稱為 Lync Server 2013 中的會議原則。 此外，舊版 Office 通訊伺服器的<STRONG>匿名 Particpants</STRONG>設定現在已成為 Lync Server 2013 會議原則中的設定。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Office 通訊伺服器 2007 R2 中，如果會議原則未設定為 [<STRONG>針對每位使用者使用</STRONG>]，則只會匯入全域原則設定。 在這種情況下，不會匯入任何其他會議原則。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果您在 Office 通訊伺服器的 2007 R2 會議原則中，將<STRONG>匿名參與者</STRONG>設定為 [<STRONG>針對每位使用者強制執行</STRONG>]，則會在遷移期間建立兩個會議原則：一個使用<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>設定為<STRONG>True</STRONG> ，另一個<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>設為<STRONG>False</STRONG>。

    
    </div>

4.  若要驗證已匯入的撥號方案，請按一下 [**語音路由**]，按一下 [**撥號方案**]，然後確認您的 Office Communicator 2007 R2 環境中的所有撥號方案都包含在清單中。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中，<STRONG>位置設定檔</STRONG>現在稱為<STRONG>撥號計畫</STRONG>。

    
    </div>

5.  若要驗證已匯入的語音原則，請按一下 [**語音路由**]，按一下 [**語音原則**]，然後確認您的 Office Communicator 2007 R2 環境中的所有語音原則都包含在清單中。
    
    <div>
    

    > [!NOTE]  
    > 如果您未將語音原則設定為在您的 Office 通訊伺服器 2007 R2 環境中<STRONG>使用每位使用者</STRONG>，則只會匯入全域原則設定。 在這種情況下，不會匯入任何其他語音原則。

    
    </div>

6.  若要驗證已匯入的語音路由，請按一下 [**語音路由**]，按一下 [**路由**]，然後確認您的 Office Communicator 2007 R2 環境中的所有語音路由都包含在清單中。

7.  若要確認已匯入 PSTN 使用設定，請按一下 [**語音路由**]，按一下 [ **PSTN 使用狀況**]，然後確認清單中包含您的 Office Communicator 2007 R2 環境中的 PSTN 使用狀況設定。

8.  若要驗證已匯入的外部存取原則，請按一下 [**同盟及外部存取**]，按一下 [**外部存取原則**]，然後確認您的 Office Communicator 2007 R2 環境中的所有外部存取原則都包含在清單中。

9.  若要驗證歸檔原則，請按一下 [**監視及**封存]，按一下 [封存**原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有存檔原則都包含在清單中。

10. 開啟 Lync Server 管理命令介面。

11. 若要驗證目前狀態原則，請在命令列輸入下列內容：
    
        Get-CsPresencePolicy
    
    透過在身分**識別**參數中查看名稱，確認您的 Office 通訊伺服器 2007 R2 環境中的所有目前狀態原則都已匯入。

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>使用 Cmdlet 驗證原則和設定

1.  開啟 Lync Server 管理命令介面。

2.  執行下表中的 Cmdlet，以驗證原則與設定。
    
    這些 Cmdlet 的語法就像下列範例所示：
    
        Get-CsConferencingPolicy
    
    如需這些 Cmdlet 的詳細資訊，請執行：
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>針對此原則或設定：</th>
<th>使用此 Cmdlet：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>目前狀態原則</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>會議原則</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>撥入存取號碼</p></td>
<td><p><strong>CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>撥號對應表</p></td>
<td><p><strong>CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>語音原則</p></td>
<td><p><strong>CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>語音路由</p></td>
<td><p><strong>CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 使用方式</p></td>
<td><p><strong>CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>Url</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部存取原則</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>存檔原則</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

