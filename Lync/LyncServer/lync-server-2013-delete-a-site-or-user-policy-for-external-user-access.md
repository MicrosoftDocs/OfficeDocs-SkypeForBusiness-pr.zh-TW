---
title: Lync Server 2013：刪除外部使用者存取的網站或使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e5539f1d6e55e94845e63b0f42c0ef855694d56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中刪除外部使用者存取的網站或使用者原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您可以刪除 [**外部存取原則**] 頁面上 [Lync Server 控制台] 中所列的任何網站或使用者原則。 刪除全域原則並不會真正將它刪除，但只會將其重設為預設設定，而不包含任何外部使用者存取選項的支援。 如需重設全域原則的詳細資訊，請參閱[在 Lync Server 2013 中重設外部使用者存取的全域原則](lync-server-2013-reset-the-global-policy-for-external-user-access.md)。

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>刪除網站或使用者原則供外部使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 索引標籤上，按一下您要刪除的網站或使用者原則，按一下 [**編輯**]，然後按一下 [**刪除**]。

5.  當系統提示您確認刪除時，請按一下 **[確定]**。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 與 Remove CsExternalAccessPolicy Cmdlet 來刪除外部存取原則。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>移除特定外部存取原則

  - 這個命令會移除已套用至雷德蒙者網站的外部存取原則：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>若要移除所有套用至每個使用者範圍的外部存取原則

  - 這個命令會移除在每個使用者作用中設定的所有外部存取原則：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>若要移除所有外部存取原則（在禁止外部使用者存取的情況下）

  - 這個命令會刪除已停用使用者存取的所有外部存取原則：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

如需詳細資訊，請參閱[Remove CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

