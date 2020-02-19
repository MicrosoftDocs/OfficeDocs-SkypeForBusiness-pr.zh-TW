---
title: Lync Server 2013： 匯出封存的資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a91ff8cbd2d6952ba4cfff8a4c5bbeb63475c342
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>從 Lync Server 2013 中匯出封存的資料

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-23_

封存在封存資料庫中的資料無法搜尋或者不是可讀格式，但是您可以使用 Export-CsArchivingData Cmdlet 從資料庫擷取記錄，並儲存為 Outlook 電子郵件 (EML) 檔案。 如需匯出封存資料的詳細資訊，請參閱操作文件中的＜[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)＞。

如果您啟用 Microsoft Exchange 整合，資料會是封存在 Exchange 2013 儲存區。 封存 Exchange 2013 中的資料是可以搜尋及探索。 如需 Exchange 2013 和 Lync Server 2013 的整合通訊支援的詳細資訊，請參閱支援文件中的[Exchange Server 與 Lync Server 2013 中支援的 SharePoint 整合](lync-server-2013-exchange-and-sharepoint-integration-support.md)。 如需存取 Exchange 中封存的資料的詳細資訊，請參閱 < Exchange 2013 文件。

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>匯出封存資料，使用 Windows PowerShell Cmdlet

您可以使用 Export-CSArchivingData Cmdlet 來匯出封存資料。 從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。

**若要匯出封存資料**

  - 此命令會匯出自 2012 年 6 月 1 日起寫入封存資料庫 atl-sql-001.litwareinc.com 中的所有封存資料。 產生的輸出檔案會儲存在資料夾 c:\\ArchivingExports。
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**若要匯出單一使用者的封存資料**

  - 下列命令會匯出單一使用者 kenmyer@litwareinc.com 的封存資料。執行時需包含 UserUri 參數，後面接使用者的 SIP 位址。例如：
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

如需詳細資訊，請參閱[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 Exchange Server 與 SharePoint 整合支援](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[管理 Lync Server 2013 封存](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

