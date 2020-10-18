---
title: 刪除現有的 Lync Phone Edition 配置設定集合
description: 刪除現有的 Lync Phone Edition 配置設定集合。
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
ms.openlocfilehash: 5137590a37b8bbb47f7445d20639157953597ca6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572859"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的 Lync Phone Edition 配置設定集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

如果您不再想要對執行 Lync Phone Edition 的裝置使用設定集合，請將其刪除。 若您刪除網站的集合，該網站中的電話就會套用全域設定。 您無法刪除全域集合。

<div>


> [!NOTE]
> 若您不想刪除集合，而只想變更部分設定。 如需如何執行此動作的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">在 Lync Server 2013 中建立或修改 Lync Phone Edition 設定的集合</A>。



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>若要刪除 Lync Phone Edition 配置設定的集合

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [用戶端]****，然後按一下 [裝置設定]**** 導覽按鈕。

4.  在「裝置設定」**** 頁面中，按一下欲刪除的集合，然後按一下 [編輯]**** 功能表，再按一下 [刪除]****。
    
    <div>
    

    > [!NOTE]
    > 若您要刪除全域集合，設定就會還原為預設值，但集合仍會存在。

    
    </div>

5.  在確認對話方塊中，按一下 [確定]****。

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 Lync Phone Edition 設定設定

您可以使用 Windows PowerShell 和 **CsUCConfiguration** 指令程式來刪除 Lync Phone Edition 設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>移除指定的 Lync Phone Edition 配置設定集合

  - 此命令會刪除套用至 Redmond 網站的 UC 電話組態設定：
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 Lync Phone Edition 設定設定

  - 此命令會移除套用至服務範圍的所有 UC 電話組態設定：
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>若要移除已停用電話鎖定的所有 Lync Phone Edition 設定設定

  - 此命令可刪除已停用電話鎖定的任何 UC 電話組態設定集合：
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

如需詳細資訊，請參閱 [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))。

</div>

</div>

<span> </span>

</div>

</div>

</div>

