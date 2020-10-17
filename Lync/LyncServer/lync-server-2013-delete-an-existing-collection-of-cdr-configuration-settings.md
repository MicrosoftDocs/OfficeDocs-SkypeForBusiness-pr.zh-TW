---
title: Lync Server 2013：刪除現有 CDR 配置設定集合
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
ms.openlocfilehash: ebf7ce01e435a0a47d3468509485e96fa669192a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514640"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中刪除現有 CDR 設定設定集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 CDR 配置設定集合。 系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。 根據設計，在網站範圍設定的設定會優先于在全域範圍設定的設定。 如果您刪除網站範圍的設定，則會使用通用設定在該網站中管理 CDR。

請注意，您也可以「刪除」全域設定。 不過，全域設定實際上不會被移除。 相反地，該集合中的所有屬性都會重設為預設值。 例如，預設會在 CDR 設定設定的集合中啟用清除。 假設您修改全域集合以停用清除。 如果您稍後刪除全域設定，所有屬性都會重設為其預設值。 在此情況下，這表示會再次啟用清除。

您可以使用 Lync Server 控制台或 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) Cmdlet 來移除 CDR 設定設定。

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>使用 Lync Server 控制台移除 CDR 設定設定

1.  在 [Lync Server 控制台] 中，按一下 [ **監控和**封存]。

2.  在 [ **詳細通話記錄** ] 索引標籤上，選取要移除之 CDR 設定的集合 (或集合) 。 若要選取多個集合，請按一下第一個集合，按住 Ctrl 鍵，然後按一下 [其他集合]。

3.  按一下 [ **編輯**]，然後按一下 [ **刪除**]。

4.  在 [Lync Server 控制台] 對話方塊中，按一下 **[確定**]。

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除 CDR 設定設定

您可以使用 Windows PowerShell 和 **Remove-CsCdrConfiguration** Cmdlet 來刪除詳細通話記錄設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>移除指定的 CDR 配置設定集合

  - 此命令會移除套用至 Redmond 網站的 CDR 設定設定：
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>移除所有套用至網站範圍的 CDR 設定設定

  - 此命令會移除所有套用至網站範圍的 CDR 設定設定：
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>移除所有停用詳細通話記錄的 CDR 設定設定

  - 此命令會移除已停用通話詳細資料記錄的所有 CDR 設定設定：
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

如需詳細資訊，請參閱 [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

