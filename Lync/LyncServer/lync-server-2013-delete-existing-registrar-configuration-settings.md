---
title: Lync Server 2013：刪除現有的註冊機構配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9fe0ee46ff823a5184ee79f3b06bb02bb68115d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中的現有註冊機構配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

請依照下列步驟刪除註冊機構。

<div>

## <a name="to-delete-registrar-configuration-settings"></a>刪除註冊機構配置設定

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [**註冊機**]。

4.  在 [**註冊機**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除之註冊機構的全部或部分名稱。

5.  在清單中，按一下您想要的註冊機構，按一下 [**編輯**]，然後按一下 [**刪除**]。

6.  按一下 [確定]****。

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除註冊機構配置設定

您可以使用 Windows PowerShell 和**CsProxyConfiguration** Cmdlet 來刪除註冊機構設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>移除一組特定的註冊機構安全設定

  - 下列命令會移除已套用至 edge Server atl-edge-011.litwareinc.com 的註冊機構安全性設定：
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的註冊機構安全性設定

  - 下列命令會移除所有已套用至註冊機構服務的註冊機構安全性設定：
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>若要移除所有允許 NTLM 驗證的註冊機構安全性設定

  - 下列命令會刪除所有註冊機構安全性設定，以允許使用 NTLM 進行用戶端驗證：
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

如需詳細資訊，請參閱[移除-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

