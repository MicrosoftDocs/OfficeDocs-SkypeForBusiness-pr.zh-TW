---
title: Lync Server 2013：刪除現有的會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29d8801c8ee58a65a60495789fdca66d16ce0c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514620"
---
# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的會議原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

遵循這些步驟即可刪除使用者層級或網站層級會議原則。

<div>


> [!NOTE]  
> 您無法刪除全域會議原則。



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>刪除網站或使用者會議原則

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  請在左導覽列中按一下 **[會議]**，然後按一下 **[會議原則]**。

4.  在會議原則清單中，按一下您要刪除的網站或使用者原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除會議原則

您可以使用 Lync Server 管理命令介面和 **Remove-CsConferencingPolicy** Cmdlet 來刪除會議原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>移除指定的會議原則

  - 下列命令可移除具有 Identity RedmondConferencingPolicy 的會議原則：
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>移除所有套用於個別使用者範圍的會議原則

  - 下列命令可移除所有設定於個別使用者範圍的會議原則：
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>移除所有允許外部使用者錄製的會議原則

  - 下列命令可移除任何允許外部使用者錄製會議的會議原則：
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

如需詳細資訊，請參閱 [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

