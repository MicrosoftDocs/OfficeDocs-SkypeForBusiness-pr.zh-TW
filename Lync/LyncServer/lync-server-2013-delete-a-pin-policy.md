---
title: Lync Server 2013：刪除 PIN 原則
description: Lync Server 2013：刪除 PIN 原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e0f1d9c22e367693f846a31b1ad2232f048965
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566569"
---
# <a name="delete-a-pin-policy-in-lync-server-2013"></a>在 Lync Server 2013 中刪除 PIN 原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

遵循下列步驟，可刪除個人識別碼 (PIN) 原則。

<div>


> [!NOTE]  
> 您無法刪除全域 PIN 原則。



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 控制台中刪除 PIN 碼原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[安全性]** 和 **[PIN 原則]**。

4.  在 **[PIN 原則]** 頁面的搜尋欄位中，輸入您要刪除之原則的完整或部分名稱。

5.  在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。

6.  按一下 **[確定]**。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 和 Remove-CsPinPolicy Cmdlet 來刪除 PIN 原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specific-pin-policy"></a>移除特定 PIN 原則

  - 這個命令將移除含有 Identity RedmondPinPolicy 的 PIN 原則：
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 PIN 原則

  - 這個命令將移除網站範圍設定的所有 PIN 原則：
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>移除允許使用共同模式的所有 PIN 原則

  - 而且，這個將移除允許使用共同模式的所有 PIN 原則：G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

如需詳細資訊，請參閱 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

