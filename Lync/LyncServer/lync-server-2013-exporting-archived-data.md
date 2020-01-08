---
title: Lync Server 2013：匯出封存的資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>從 Lync Server 2013 匯出已歸檔的資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

歸檔資料庫中封存的資料無法以可讀取的格式進行搜尋，但您可以使用 Export CsArchivingData Cmdlet 來從資料庫提取記錄，並將其儲存為 Outlook 電子郵件（.EML）檔案。 如需有關匯出封存資料的詳細資訊，請參閱作業檔中的[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 。

如果您啟用 Microsoft Exchange 整合，資料會封存在 Exchange 2013 儲存區中。 以 Exchange 2013 存檔的資料是可搜尋且可探索的。 如需 Exchange 2013 和 Lync Server 2013 整合的支援的相關詳細資料，請參閱支援檔中的[Lync server 2013 中的 Exchange Server 和 SharePoint 整合支援](lync-server-2013-exchange-and-sharepoint-integration-support.md)。 如需存取 Exchange 中已歸檔資料的詳細資訊，請參閱 Exchange 2013 檔。

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 匯出存檔資料

您可以使用 Export CSArchivingData Cmdlet 來匯出封存資料。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

**匯出存檔資料**

  - 這個命令會從2012年6月1日起，匯出已寫入封存資料庫 atl-sql-001.litwareinc.com 的所有存檔資料。 產生的輸出檔案會儲存在資料夾 C：\\ArchivingExports 中。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**若要匯出單一使用者的存檔資料**

  - 下列命令會匯出單一使用者的存檔資料： kenmyer@litwareinc.com。 這是透過包括 UserUri 參數及使用者的 SIP 位址來完成。 例如：
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

如需詳細資訊，請參閱[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 Exchange Server 與 SharePoint 整合支援](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[管理 Lync Server 2013 封存](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

