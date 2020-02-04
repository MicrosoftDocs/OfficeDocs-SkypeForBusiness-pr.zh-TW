---
title: Lync Server 2013：刪除現有的 CDR 配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50df73d59c588094693009ab4c84f2a7809ba5f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有的 CDR 配置設定集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。 此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 CDR 配置設定。 系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。 根據設計，在網站範圍設定的設定會優先于在全域範圍中設定的設定。 如果您刪除網站範圍的設定，則會使用全域設定在該網站中管理 CDR。

請注意，您也可以 [刪除] 全域設定。 不過，全域設定將不會實際移除。 相反地，該集合中的所有屬性都會重設為預設值。 例如，在 CDR 配置設定的集合中啟用 [清除]。 假設您修改全域集合，以便停用清除功能。 如果您稍後刪除全域設定，所有屬性都將會重設為預設值。 在這種情況下，這表示清除會再次啟用。

您可以使用 Lync Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) Cmdlet 來移除 CDR 配置設定。

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>使用 Lync Server 控制台移除 CDR 配置設定

1.  在 Lync Server [控制台] 中，按一下 [**監視及**封存]。

2.  在 [**通話詳細資料記錄**] 索引標籤上，選取要移除的 CDR 設定的集合（或 [收藏]）。 若要選取多個收藏，請按一下第一個收藏，按住 Ctrl 鍵，然後按一下 [其他集合]。

3.  按一下 [**編輯**]，然後按一下 [**刪除**]。

4.  在 [Lync Server 控制台] 對話方塊中，按一下 **[確定]**。

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 CDR 配置設定

您可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來刪除通話詳細資料錄製設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>移除指定的 CDR 配置設定集合

  - 這個命令會移除套用至雷德蒙網站的 CDR 設定設定：
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>移除套用至網站範圍的所有 CDR 設定設定

  - 這個命令會移除所有適用于網站範圍的 CDR 設定設定：
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>若要移除停用通話詳細資料錄製的所有 CDR 設定設定

  - 這個命令會移除已停用通話詳細資料錄製的所有 CDR 設定設定：
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

如需詳細資訊，請參閱[Remove CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

