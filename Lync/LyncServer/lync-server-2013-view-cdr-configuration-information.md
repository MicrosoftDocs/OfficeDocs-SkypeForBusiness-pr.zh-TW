---
title: Lync Server 2013：查看 CDR 配置資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa03ab1ce52c98746657c0314760c902f295589
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看 CDR 配置資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。 此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 CDR 配置設定。 系統管理員也可以選擇建立可套用至個別網站的自訂設定集合。 您可以使用 Lync Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) Cmdlet 來查看貴組織中使用的 CDR 配置設定。

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 來查看 CDR 配置資訊

1.  在 Lync Server [控制台] 中，按一下 [**監視及**封存]。

2.  [**通話詳細資料記錄**] 索引標籤中會顯示所有 CDR 設定設定的清單;針對每個設定集合，您會看到集合**名稱**;是否已啟用 CDR （ **cdr**屬性）;以及是否已啟用清除（ **CDR 清除**屬性）。 若要查看集合的詳細資訊，請按兩下該集合，或選取適當的集合，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。 請注意，您一次只能針對單一的 CDR 配置設定集合查看詳細資訊。

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看 CDR 配置資訊

您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來查看 CDR 配置設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-cdr-configuration-information"></a>若要查看 CDR 配置資訊

  - 若要查看所有 CDR 配置設定的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsCdrConfiguration
    
    這會傳回如下所示的資訊：
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

如需詳細資訊，請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

