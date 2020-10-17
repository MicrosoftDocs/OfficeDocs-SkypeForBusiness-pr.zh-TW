---
title: Lync Server 2013：查看 CDR 設定資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60ea87c488c84f76e60d3a4ad1815e8cfcb3d078
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506630"
---
# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看 CDR 設定資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

詳細通話記錄 (CDR) 讓您能夠追蹤點對點即時訊息工作階段、Voice over Internet Protocol (VoIP) 電話通話，以及會議通話之類的使用狀況。這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 CDR 配置設定集合。 系統管理員也可以選擇建立自訂的設定集合，以套用於個別網站。 您可以使用 Lync Server 控制台或 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) Cmdlet 來查看組織中所使用的 CDR 設定設定。

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>使用 Lync Server 控制台查看 CDR 設定資訊

1.  在 [Lync Server 控制台] 中，按一下 [ **監控和**封存]。

2.  您所有 CDR 組態設定的清單將在 **[詳細通話記錄]** 索引標籤中顯示；在每一個設定集合中，您將會看到 **[名稱]** 集合；無論是否啟用 CDR (**CDR** 屬性)；無論是否啟用清除 (**CDR purging** 屬性)。若要檢視有關集合的詳細資訊，請在該集合按兩下滑鼠，或選取合適的集合，按一下 **[編輯]**，然後按一下 **[顯示詳細資訊]**。請記住，您一次只能檢視單一 CDR 組態設定集合的詳細資訊。

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 CDR 設定資訊

您可以使用 Windows PowerShell 和 Get-CsCdrConfiguration Cmdlet 來查看 CDR 設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-cdr-configuration-information"></a>檢視 CDR 組態資訊

  - 若要查看所有 CDR 設定設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsCdrConfiguration
    
    如此將傳回類似如下的資訊：
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

如需詳細資訊，請參閱 [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

