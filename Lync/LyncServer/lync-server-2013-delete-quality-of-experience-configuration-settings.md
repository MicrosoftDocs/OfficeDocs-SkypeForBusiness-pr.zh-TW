---
title: Lync Server 2013：刪除體驗配置設定的品質
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
ms.openlocfilehash: bef2a59243d065f74c09dd4bc5c3aeb6a4451bbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中的 [體驗品質] 設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

經驗品質（QoE）度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）的數量。 這些度量單位會與其他資料（例如通話明細記錄）之外，儲存在資料庫中，讓您可以啟用和停用與其他資料錄製無關的 QoE。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 QoE 配置設定集合。 系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。 根據設計，在網站範圍設定的設定會優先于在全域範圍中設定的設定。 如果您刪除網站範圍的設定，就會使用全域設定在該網站中管理 QoE。

請注意，您也可以 [刪除] 全域設定。 不過，全域設定將不會實際移除。 相反地，該集合中的所有屬性都會重設為預設值。 例如，在 QoE 配置設定的集合中啟用 [清除]。 假設您修改全域集合，以便停用清除功能。 如果您稍後刪除全域設定，所有屬性都將會重設為預設值。 在這種情況下，這表示清除會再次啟用。

您可以使用 Lync Server [控制台] 或使用[remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) Cmdlet 來移除 QoE 設定設定。

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 刪除 QoE 配置設定

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。

4.  在 [**體驗品質資料**] 頁面上，按一下您要的原則，按一下 [**編輯**]，然後按一下 [**刪除**]。

5.  按一下 [確定]****。

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 QoE 配置設定

您可以使用 Windows PowerShell 和**Remove-CsQoEConfiguration** Cmdlet 來刪除 QoE 設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>移除指定的 QoE 配置設定集合

  - 這個命令會移除套用至雷德蒙網站的 QoE 設定設定：
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的 QoE 設定設定

  - 這個命令會移除所有套用至網站範圍的 QoE 設定：
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>若要移除 QoE 監視功能停用的所有 QoE 設定設定

  - 這個命令會移除已停用 QoE 監視的所有 QoE 設定設定：
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

如需詳細資訊，請參閱[移除-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

