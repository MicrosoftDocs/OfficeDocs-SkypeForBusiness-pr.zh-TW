---
title: 刪除現有的用戶端版本配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a71df7af1f0a6158cb61e780b44ed4227d32018
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中現有的用戶端版本配置設定集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

如果您想要移除先前針對網站設定的用戶端設定設定，您可以移除 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 中的設定。

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 移除用戶端配置設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本**設定] 瀏覽按鈕。

4.  選取網站，按一下 [**編輯**]，按一下 [**刪除**]，然後按一下 **[確定]**。

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除用戶端版本配置設定

您可以使用**CsClientVersionConfiguration** Cmdlet 刪除用戶端版本配置設定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>移除指定的用戶端版本配置設定集合

  - 下列命令會移除套用至雷德蒙網站的用戶端版本設定設定：
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的用戶端版本設定設定

  - 這個命令會移除在網站範圍中設定的所有用戶端版本設定設定：
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>根據 DefaultAction 屬性的值移除所有用戶端版本設定設定

  - 這個命令會移除已將預設動作設定為「封鎖」的所有用戶端版本配置設定：
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

如需詳細資訊，請參閱[Remove CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

