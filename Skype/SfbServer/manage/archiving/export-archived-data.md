---
title: 在商務用 Skype Server 中匯出封存的資料
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要：瞭解如何匯出商務用 Skype 伺服器的封存資料。
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095377"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="7785a-103">在商務用 Skype Server 中匯出封存的資料</span><span class="sxs-lookup"><span data-stu-id="7785a-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="7785a-104">**摘要：** 瞭解如何匯出商務用 Skype 伺服器的封存資料。</span><span class="sxs-lookup"><span data-stu-id="7785a-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="7785a-105">封存資料庫中封存的資料無法以可讀取的格式進行搜尋，但是您可以使用 **Export-CsArchivingData** Cmdlet 從資料庫提取記錄，並將其儲存為 Outlook 電子郵件 (.eml) 檔案。</span><span class="sxs-lookup"><span data-stu-id="7785a-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="7785a-106">如果您啟用 Microsoft Exchange 整合，資料會封存在 Exchange 存放區中。</span><span class="sxs-lookup"><span data-stu-id="7785a-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="7785a-107">Exchange 中封存的資料是可搜尋且可探索的。</span><span class="sxs-lookup"><span data-stu-id="7785a-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="7785a-108">如需存取 Exchange 中已封存資料的詳細資訊，請參閱 Exchange 檔。</span><span class="sxs-lookup"><span data-stu-id="7785a-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7785a-109">使用 Windows PowerShell Cmdlet 匯出封存資料</span><span class="sxs-lookup"><span data-stu-id="7785a-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7785a-110">您可以使用 Export-CSArchivingData Cmdlet 來匯出封存的資料。</span><span class="sxs-lookup"><span data-stu-id="7785a-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="7785a-111">下列命令會匯出從2012年6月1日起寫入封存資料庫 atl-sql-001.contoso.com 的所有封存資料。</span><span class="sxs-lookup"><span data-stu-id="7785a-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="7785a-112">所產生的輸出檔案會儲存在 C:\ArchivingExports 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="7785a-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="7785a-113">下列命令會匯出單一使用者的封存資料： kenmyer@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="7785a-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="7785a-114">若要執行此操作，您可以加入 UserUri 參數後接使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="7785a-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="7785a-115">例如：</span><span class="sxs-lookup"><span data-stu-id="7785a-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="7785a-116">如需詳細資訊，請參閱 [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="7785a-116">For more information, see the help topic for the [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
