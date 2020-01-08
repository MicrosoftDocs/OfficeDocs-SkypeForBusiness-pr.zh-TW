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

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="ed7a2-102">從 Lync Server 2013 匯出已歸檔的資料</span><span class="sxs-lookup"><span data-stu-id="ed7a2-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed7a2-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ed7a2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ed7a2-104">歸檔資料庫中封存的資料無法以可讀取的格式進行搜尋，但您可以使用 Export CsArchivingData Cmdlet 來從資料庫提取記錄，並將其儲存為 Outlook 電子郵件（.EML）檔案。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="ed7a2-105">如需有關匯出封存資料的詳細資訊，請參閱作業檔中的[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="ed7a2-106">如果您啟用 Microsoft Exchange 整合，資料會封存在 Exchange 2013 儲存區中。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="ed7a2-107">以 Exchange 2013 存檔的資料是可搜尋且可探索的。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="ed7a2-108">如需 Exchange 2013 和 Lync Server 2013 整合的支援的相關詳細資料，請參閱支援檔中的[Lync server 2013 中的 Exchange Server 和 SharePoint 整合支援](lync-server-2013-exchange-and-sharepoint-integration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="ed7a2-109">如需存取 Exchange 中已歸檔資料的詳細資訊，請參閱 Exchange 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ed7a2-110">使用 Windows PowerShell Cmdlet 匯出存檔資料</span><span class="sxs-lookup"><span data-stu-id="ed7a2-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ed7a2-111">您可以使用 Export CSArchivingData Cmdlet 來匯出封存資料。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="ed7a2-112">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ed7a2-113">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="ed7a2-114">**匯出存檔資料**</span><span class="sxs-lookup"><span data-stu-id="ed7a2-114">**To export archiving data**</span></span>

  - <span data-ttu-id="ed7a2-115">這個命令會從2012年6月1日起，匯出已寫入封存資料庫 atl-sql-001.litwareinc.com 的所有存檔資料。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="ed7a2-116">產生的輸出檔案會儲存在資料夾 C：\\ArchivingExports 中。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="ed7a2-117">**若要匯出單一使用者的存檔資料**</span><span class="sxs-lookup"><span data-stu-id="ed7a2-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="ed7a2-118">下列命令會匯出單一使用者的存檔資料： kenmyer@litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="ed7a2-119">這是透過包括 UserUri 參數及使用者的 SIP 位址來完成。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="ed7a2-120">例如：</span><span class="sxs-lookup"><span data-stu-id="ed7a2-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="ed7a2-121">如需詳細資訊，請參閱[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ed7a2-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed7a2-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="ed7a2-122">See Also</span></span>


[<span data-ttu-id="ed7a2-123">Lync Server 2013 中的 Exchange Server 與 SharePoint 整合支援</span><span class="sxs-lookup"><span data-stu-id="ed7a2-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="ed7a2-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="ed7a2-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="ed7a2-125">管理 Lync Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="ed7a2-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

