---
title: 刪除現有的 Lync Phone Edition 配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中現有的 Lync Phone Edition 配置設定集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

如果您不想再使用執行 Lync Phone Edition 之裝置的設定集合，請將其刪除。 如果您刪除網站的集合，全域設定將會套用至該網站中的手機。 您無法刪除全域集合。

<div>


> [!NOTE]
> 您可能只想變更部分設定，而不是刪除收藏。 如需如何執行此動作的詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">在 Lync Server 2013 中建立或修改 Lync 手機版配置設定的集合</A>。



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>刪除 Lync Phone Edition 設定的集合

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置配置**] 瀏覽按鈕。

4.  在 [**裝置**設定] 頁面上，按一下您要刪除的集合，按一下 [**編輯**] 功能表，然後按一下 [**刪除**]。
    
    <div>
    

    > [!NOTE]
    > 如果您刪除全域集合，這些設定就會還原為預設設定。 收藏不會消失。

    
    </div>

5.  在確認方塊中，按一下 **[確定]**。

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 Lync Phone Edition 設定設定

您可以使用 Windows PowerShell 和**CsUCConfiguration** Cmdlet 來刪除 Lync Phone Edition 設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>移除指定的 Lync Phone Edition 配置設定集合

  - 這個命令會刪除套用至雷德蒙者網站的 UC 手機設定設定：
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 Lync 手機版設定設定

  - 這個命令會移除所有套用至服務範圍的 UC 電話設定：
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>若要移除電話封鎖停用的所有 Lync 手機版設定設定

  - 這個命令會刪除已停用電話封鎖的任何 UC 手機設定的集合：
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

如需詳細資訊，請參閱[移除-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))。

</div>

</div>

<span> </span>

</div>

</div>

</div>

