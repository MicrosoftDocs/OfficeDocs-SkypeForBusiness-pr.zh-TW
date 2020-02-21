---
title: Lync Server 2013： 建立或修改 CDR 組態設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 828c02e11d9e5adfe7028dd8d224c10df14c2247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>建立或修改的 Lync Server 2013 中的 CDR 組態設定集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-23_

詳細通話記錄 (CDR) 可讓您追蹤使用情況的對等立即訊息工作階段，Voice over Internet Protocol (VoIP) 通話，等和會議會呼叫。 這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。

當您安裝 Microsoft Lync Server 2013 單一時，為您建立的 CDR 組態設定全域集合。 系統管理員也可以選擇建立網站範圍的自訂設定。 只要使用這些網站範圍的設定，其優先順序就高於全域設定。 例如，如果您建立 Redmond 網站的網站範圍設定然後那些設定 （而不是通用設定]） 將會用來管理在 Redmond 的 CDR。

您可以使用 [Lync Server Control Panel] 或 [ [New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 建立 CDR 組態設定。 您可以使用 Lync Server Control Panel 或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 來修改現有的設定。 如果您用來建立或修改設定 Lync Server Control Panel，會是您可以使用下列選項：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell 參數</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>身分識別</p></td>
<td><p>要建立之 CDR 組態設定的唯一識別碼。 只能在網站範圍建立這些設定。</p></td>
</tr>
<tr class="even">
<td><p>啟用監視 Cdr</p></td>
<td><p>EnableCDR</p></td>
<td><p>表示是否啟用 CDR。</p></td>
</tr>
<tr class="odd">
<td><p>啟用 Cdr 的清除</p></td>
<td><p>EnablePurging</p></td>
<td><p>會指出會定期從 CDR 資料庫刪除 CDR 記錄。</p></td>
</tr>
<tr class="even">
<td><p>將 Cdr 保留最大持續期限 （天）</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>會指出的 CDR 記錄仍會保留 CDR 資料庫中的天數。 將會自動刪除任何記錄早於指定天數。 （請注意，清除不會發生只有是否清除已啟用）。</p></td>
</tr>
<tr class="odd">
<td><p>將錯誤報告資料保留最大持續期限 （天）</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>會指出的 CDR 錯誤報告所保留的天數。 將會自動刪除早於指定天數任何報告。 CDR 錯誤報告是由用戶端應用程式上傳診斷報告。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> New-cscdrconfiguration 和 Set-cscdrconfiguration cmdlet 包含 Lync Server 控制台不提供的額外選項。 請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-cscdrconfiguration</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-cscdrconfiguration</A>說明主題中的詳細資訊。



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>若要使用 Lync Server 控制台建立 CDR 組態設定

1.  Lync Server 控制台] 中按一下 [**監控和封存**]。

2.  在 [**詳細通話記錄**] 索引標籤中，按一下 [**新增**]。

3.  在 [**選取網站**] 對話方塊中，選取要建立新的組態設定的所在的網站。 如果 [對話方塊] 方塊是空的這表示所有網站已指定的 CDR 組態設定集合。 每個網站受限於單一這類集合。 在此情況下您可以刪除，並是然後重新建立與設定，或只是修改現有的設定。

4.  在 [**新詳細通話記錄 (CDR) 設定**] 對話方塊中，進行想要的選擇，然後按一下 [**認可]**。

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>若要使用 Lync Server 控制台修改現有的 CDR 組態設定

1.  Lync Server 控制台] 中按一下 [**監控和封存**]。

2.  連按兩下 [設定以進行修改，或選取集合，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**的集合。 請注意，您只能修改一次的單一集合。 若要讓多個集合相同的變更，請改為使用 Lync Server 管理命令介面。

3.  在 [**編輯詳細通話記錄 (CDR) 設定**] 對話方塊中，進行想要的選擇，然後按一下 [**認可]**。

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 CDR 組態設定

您可以建立 CDR 組態設定也可以建立使用 Windows PowerShell 和**New-cscdrconfiguration** cmdlet。 從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，您可以執行此 cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>若要建立新的 CDR 組態設定集合

  - 此命令會建立新的 CDR 組態設定套用至 Redmond 網站集合：
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>若要建立一群 CDR 組態設定，停用詳細通話記錄

  - 因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。 若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。 例如，若要建立之呼叫的詳細組態的集合，根據預設，允許設定停用詳細通話記錄使用這類命令：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>若要建立新的 CDR 組態設定集合時指定多個屬性值

  - 您可以修改多個屬性值包括多個參數。 例如，此命令會設定要保留 30 天和錯誤報告的詳細通話記錄 90 天的新設定：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

如需詳細資訊，請參閱[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

