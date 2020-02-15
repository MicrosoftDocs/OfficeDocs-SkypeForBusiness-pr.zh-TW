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
ms.openlocfilehash: 4bb0bcb30c49a44fe92920d4db77d6bf9697cd9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="f52d4-102">從 Lync Server 2013 中匯出封存的資料</span><span class="sxs-lookup"><span data-stu-id="f52d4-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f52d4-103">_**上次修改主題：** 2013年-02-23_</span><span class="sxs-lookup"><span data-stu-id="f52d4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f52d4-104">封存在封存資料庫中的資料無法搜尋或者不是可讀格式，但是您可以使用 Export-CsArchivingData Cmdlet 從資料庫擷取記錄，並儲存為 Outlook 電子郵件 (EML) 檔案。</span><span class="sxs-lookup"><span data-stu-id="f52d4-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="f52d4-105">如需匯出封存資料的詳細資訊，請參閱操作文件中的＜[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)＞。</span><span class="sxs-lookup"><span data-stu-id="f52d4-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="f52d4-106">如果您啟用 Microsoft Exchange 整合，資料會是封存在 Exchange 2013 儲存區。</span><span class="sxs-lookup"><span data-stu-id="f52d4-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="f52d4-107">封存 Exchange 2013 中的資料是可以搜尋及探索。</span><span class="sxs-lookup"><span data-stu-id="f52d4-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="f52d4-108">如需 Exchange 2013 和 Lync Server 2013 的整合通訊支援的詳細資訊，請參閱支援文件中的[Exchange Server 與 Lync Server 2013 中支援的 SharePoint 整合](lync-server-2013-exchange-and-sharepoint-integration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="f52d4-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="f52d4-109">如需存取 Exchange 中封存的資料的詳細資訊，請參閱 < Exchange 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="f52d4-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f52d4-110">匯出封存資料，使用 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f52d4-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f52d4-111">您可以使用 Export-CSArchivingData Cmdlet 來匯出封存資料。</span><span class="sxs-lookup"><span data-stu-id="f52d4-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="f52d4-112">從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f52d4-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f52d4-113">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="f52d4-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="f52d4-114">**若要匯出封存資料**</span><span class="sxs-lookup"><span data-stu-id="f52d4-114">**To export archiving data**</span></span>

  - <span data-ttu-id="f52d4-115">此命令會匯出自 2012 年 6 月 1 日起寫入封存資料庫 atl-sql-001.litwareinc.com 中的所有封存資料。</span><span class="sxs-lookup"><span data-stu-id="f52d4-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="f52d4-116">產生的輸出檔案會儲存在資料夾 c:\\ArchivingExports。</span><span class="sxs-lookup"><span data-stu-id="f52d4-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="f52d4-117">**若要匯出單一使用者的封存資料**</span><span class="sxs-lookup"><span data-stu-id="f52d4-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="f52d4-p105">下列命令會匯出單一使用者 kenmyer@litwareinc.com 的封存資料。執行時需包含 UserUri 參數，後面接使用者的 SIP 位址。例如：</span><span class="sxs-lookup"><span data-stu-id="f52d4-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="f52d4-121">如需詳細資訊，請參閱[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="f52d4-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f52d4-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f52d4-122">See Also</span></span>


[<span data-ttu-id="f52d4-123">Lync Server 2013 中的 Exchange Server 與 SharePoint 整合支援</span><span class="sxs-lookup"><span data-stu-id="f52d4-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="f52d4-124">Export-csarchivingdata</span><span class="sxs-lookup"><span data-stu-id="f52d4-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="f52d4-125">管理 Lync Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="f52d4-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

