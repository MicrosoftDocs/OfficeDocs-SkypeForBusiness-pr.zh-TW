---
title: 確認組態設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508410"
---
# <a name="verify-configuration-settings"></a>確認組態設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

在您合併拓撲並執行 **Import-CsLegacyConfiguration** Cmdlet 後，請確認您的 Office 通訊伺服器 2007 R2 原則和設定已匯入 Lync Server 2013。 下表列出您應確認的原則及設定。

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>移轉後所需檢查的原則與設定


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若是使用此工作量：</th>
<th>檢查下列原則與設定：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>立即訊息 (IM) 和會議</p></td>
<td><p>目前狀態原則</p>
<p>會議原則</p></td>
</tr>
<tr class="even">
<td><p>電話撥入式會議</p></td>
<td><p>撥入存取號碼</p>
<p>撥號計劃</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>語音原則</p>
<p>語音路由</p>
<p>撥號計劃</p>
<p>PSTN 使用方式設定</p></td>
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
<td><p>封存原則</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>驗證原則與設定

1.  在您的 Office 通訊伺服器 2007 R2 環境中，記下 [撥號對應表] (以前稱為位置設定檔的名稱) 、撥入存取號碼 (會議應答存取電話號碼和地區) 、語音路由以及上表所列的原則，除了用於 Communicator Web Access 的 URLs 之外。

2.  在 Lync Server 2013 前端伺服器上，開啟 [Lync Server 控制台]。

3.  若要驗證匯入的會議原則，請在左窗格中，依序按一下 [ **會議**]、[ **會議原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有會議原則都包含在清單中。
    
    <div>
    

    > [!NOTE]  
    > 先前版本的 Office 通訊伺服器的 <STRONG>會議</STRONG> 原則現在稱為 Lync Server 2013 中的會議原則。 此外，舊版 Office 通訊伺服器的 <STRONG>匿名 Particpants</STRONG> 設定現在是 Lync Server 2013 會議原則中的設定。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Office 通訊伺服器 2007 R2 中，如果會議原則並未設定為 [ <STRONG>每位使用者使用</STRONG>]，則只會匯入全域原則設定。 在此情況下，將不會匯入其他的會議原則。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果在您的 Office 通訊伺服器 2007 R2 會議原則中，將 <STRONG>匿名參與者</STRONG> 設定為 <STRONG>針對每位使用者強制執行</STRONG> ，則在遷移期間會建立兩個會議原則：其中一個 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 設定為 True，另一個 <STRONG>則</STRONG> 使用 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 設定為 <STRONG>False</STRONG>。

    
    </div>

4.  若要驗證匯入的撥號對應表，請依序按一下 **[語音路由]** 與 **[撥號對應表]**，然後驗證您 Office Communicator 2007 R2 環境的所有撥號對應表都包含在清單中。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中， <STRONG>位置設定檔</STRONG> 現在稱為 <STRONG>撥號</STRONG>對應表。

    
    </div>

5.  若要驗證匯入的語音原則，請依序按一下 **[語音路由]** 與 **[語音原則]**，然後驗證您 Office Communicator 2007 R2 環境的所有語音原則都包含在清單中。
    
    <div>
    

    > [!NOTE]  
    > 如果您的 Office 通訊伺服器 2007 R2 環境中的 <STRONG>每位使用者</STRONG> 未設定語音原則，則只會匯入全域原則設定。 在此情況下，將不會匯入其他的語音原則。

    
    </div>

6.  若要驗證匯入的語音路由，請依序按一下 **[語音路由]** 及 **[路由]**，然後驗證您 Office Communicator 2007 R2 環境中的所有語音路由都包含在清單中。

7.  若要驗證匯入的 PSTN 使用方式設定，請依序按一下 **[語音路由]** 及 **[PSTN 使用方式]**，然後驗證您 Office Communicator 2007 R2 環境中的 PSTN 使用方式設定包含在清單中。

8.  若要驗證匯入的外部存取原則，請依序按一下 **[同盟與外部存取]** 及 **[外部存取原則]**，然後驗證您 Office Communicator 2007 R2 環境中的所有外部存取原則都包含在清單中。

9.  若要驗證封存原則，請依序按一下 [ **監視與**封存]、[封存 **原則**]，然後確認您的 Office 通訊伺服器 2007 R2 環境中的所有封存原則都包含在清單中。

10. 開啟 Lync Server 管理命令介面。

11. 若要驗證命令列的顯示狀態原則，請輸入下列內容：
    
        Get-CsPresencePolicy
    
    透過查看 **Identity** 參數中的名稱，確認已匯入 Office 通訊伺服器 2007 R2 環境中的所有目前狀態原則。

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>使用 Cmdlet 檢查原則與設定

1.  開啟 Lync Server 管理命令介面。

2.  執行下表中的 Cmdlet，可以檢查原則及設定。
    
    這些 Cmdlet 的語法會類似下列範例：
    
        Get-CsConferencingPolicy
    
    如需這些 Cmdlet 的詳細資料，請執行：
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>若為下列原則或設定：</th>
<th>請使用此 Cmdlet：</th>
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
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>撥號對應表</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>語音原則</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>語音路由</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 使用方式</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部存取原則</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>封存原則</p></td>
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

