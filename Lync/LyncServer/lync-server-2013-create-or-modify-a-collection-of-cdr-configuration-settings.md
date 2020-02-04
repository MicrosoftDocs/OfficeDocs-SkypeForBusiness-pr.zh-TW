---
title: Lync Server 2013：建立或修改 CDR 配置設定的集合
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
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改 CDR 配置設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。 此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一的 [CDR 設定] 設定的全域集合。 系統管理員也可以選擇在網站範圍中建立自訂設定。 只要使用這些網站範圍的設定，就會優先于全域設定。 例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙者中的 CDR。

您可以使用 Lync Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet 來建立 CDR 配置設定。 您可以使用 Lync Server [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 來修改現有的設定。 如果您使用 Lync Server [控制台] 來建立或修改設定，您可以使用下列選項：


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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>Identity</p></td>
<td><p>所建立的 CDR 配置設定的唯一識別碼。 這些設定只能在網站範圍建立。</p></td>
</tr>
<tr class="even">
<td><p>啟用 CDRs 的監控</p></td>
<td><p>EnableCDR</p></td>
<td><p>指出是否已啟用 CDR。</p></td>
</tr>
<tr class="odd">
<td><p>啟用清除 CDRs</p></td>
<td><p>EnablePurging</p></td>
<td><p>指出 CDR 記錄是否會定期從 CDR 資料庫中刪除。</p></td>
</tr>
<tr class="even">
<td><p>保留 CDRs 的最大持續時間（天）</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>表示 CDR 記錄將保留在 CDR 資料庫中的天數。 任何超過指定天數的記錄都會自動刪除。 （請注意，清除功能只會在已啟用清除時才會發生。）</p></td>
</tr>
<tr class="odd">
<td><p>針對最大持續時間（天）保留錯誤報表資料</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>表示保留 CDR 錯誤報表的天數。 任何超過指定天數的報告都會自動刪除。 CDR 錯誤報表是用戶端應用程式上傳的診斷報告。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> CsCdrConfiguration 和 CsCdrConfiguration Cmdlet 包括在 Lync Server [控制台] 中無法使用的其他選項。 如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">新的-CsCdrConfiguration</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">設定 CsCdrConfiguration</A>的協助主題。



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立 CDR 配置設定

1.  在 Lync Server [控制台] 中，按一下 [**監視及**封存]。

2.  在 [**通話詳細資料記錄**] 索引標籤上，按一下 [**新增**]。

3.  在 [**選取網站**] 對話方塊中，選取要建立新配置設定的網站。 如果對話方塊是空白的，則表示您的所有網站都已指派給 CDR 配置設定的集合。 每個網站僅限一個此類集合。 在這種情況下，您可以刪除並重新建立設定，或直接修改現有的設定。

4.  在 [**新增通話詳細資料錄製（CDR）設定**] 對話方塊中，選取所要的選項，然後按一下 [**確認**]。

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 修改現有的 CDR 配置設定

1.  在 Lync Server [控制台] 中，按一下 [**監視及**封存]。

2.  按兩下要修改的設定集合，或選取該收藏，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。 請注意，您一次只能修改單一集合。 若要對多個收藏進行相同的變更，請改用 Lync Server 管理命令介面。

3.  在 [**編輯通話詳細資料錄製（CDR）] 設定**對話方塊中，選取所要的選項，然後按一下 [**確認**]。

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 CDR 配置設定

您也可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來建立 CDR 配置設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>若要建立新的 CDR 配置設定集合

  - 這個命令會建立套用至雷德蒙網站的 CDR 設定設定的新集合：
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>若要建立停用通話詳細資料錄製的 CDR 配置設定集合

  - 因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立通話詳細資料設定的集合，根據預設，允許停用通話詳細資料錄製使用如下所示的命令：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>建立新的 CDR 配置設定集合時，指定多個屬性值

  - 您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會將新設定設定為將呼叫詳細資料記錄保持在30天，並將錯誤報表保留90天：
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

如需詳細資訊，請參閱[新版-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

