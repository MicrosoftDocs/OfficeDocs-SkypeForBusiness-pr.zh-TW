---
title: Lync Server 2013：刪除經驗品質設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ab6d90109d177fde84f8693cb4d14b5d8a6fdb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525540"
---
# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中刪除經驗品質設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

「經驗品質 (QoE)」計量在追蹤組織中進行之音訊和視訊通話的品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 等項目的數量。這些計量會儲存在與其他資料 (例如詳細通話記錄) 不同的資料庫中，讓您可獨立於其他資料記錄來啟用和停用 QoE。

當您安裝 Microsoft Lync Server 2013 時，會為您建立單一、全域的 QoE 配置設定集合。 系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。 根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。 如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 QoE。

請注意，您也可以「刪除」全域設定。 不過，全域設定實際上不會被移除。 相反地，該集合中的所有屬性都會重設為預設值。 例如，預設會在 QoE 設定設定的集合中啟用清除。 假設您修改全域集合以停用清除。 如果您稍後刪除全域設定，所有屬性都會重設為其預設值。 在此情況下，這表示會再次啟用清除。

您可以使用 Lync Server 控制台或使用 [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) Cmdlet 來移除 QoE 設定設定。

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台刪除 QoE 配置設定

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4.  在 [ **經驗品質資料** ] 頁面上，按一下您要的原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。

5.  按一下 [確定]****。

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 QoE 配置設定

您可以使用 Windows PowerShell 和 **Remove-CsQoEConfiguration** Cmdlet 刪除 QoE 的設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>移除指定的 QoE 配置設定集合

  - 此命令會移除套用至 Redmond 網站的 QoE 設定：
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 QoE 設定設定

  - 此命令會移除所有套用至網站範圍的 QoE 設定設定：
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>移除所有停用 QoE 監控的 QoE 設定設定

  - 這個命令會移除所有已停用 QoE 監控的 QoE 設定設定：
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

如需詳細資訊，請參閱 [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

