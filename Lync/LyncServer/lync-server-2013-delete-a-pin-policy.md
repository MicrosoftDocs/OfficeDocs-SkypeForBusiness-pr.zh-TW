---
title: Lync Server 2013：刪除 PIN 原則
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
ms.openlocfilehash: cc11f1383ec652c512fe5542d9a6780ce028c516
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a>刪除 Lync Server 2013 中的 PIN 原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

請依照下列步驟刪除個人識別碼（PIN）原則。

<div>


> [!NOTE]  
> 您無法刪除全域 PIN 原則。



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 的 [控制台] 中刪除 PIN 原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **PIN 規則**]。

4.  在 [ **PIN 原則**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除之原則的全部或部分名稱。

5.  在原則清單中，按一下您想要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。

6.  按一下 [確定]****。

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 PIN 原則

您可以使用 Windows PowerShell 與 Remove CsPinPolicy Cmdlet 來刪除 PIN 原則。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specific-pin-policy"></a>移除特定的 PIN 原則

  - 這個命令會移除具有身分識別 RedmondPinPolicy 的 PIN 原則：
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 PIN 原則

  - 這個命令會移除在網站範圍中設定的所有 PIN 原則：
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>若要移除所有允許使用常見模式的 PIN 原則

  - 如此一來，會移除所有允許使用常見模式的 PIN 原則： G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

如需詳細資訊，請參閱[Remove CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

