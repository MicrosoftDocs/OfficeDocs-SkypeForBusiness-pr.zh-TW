---
title: 在商務用 Skype Server 中匯出已歸檔的資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '摘要: 瞭解如何匯出商務用 Skype Server 的存檔資料。'
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190360"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="1898c-103">在商務用 Skype Server 中匯出已歸檔的資料</span><span class="sxs-lookup"><span data-stu-id="1898c-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="1898c-104">**摘要:** 瞭解如何匯出商務用 Skype Server 的存檔資料。</span><span class="sxs-lookup"><span data-stu-id="1898c-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="1898c-105">歸檔資料庫中封存的資料無法以可讀取的格式進行搜尋, 但您可以使用**Export CsArchivingData** Cmdlet 來從資料庫提取記錄, 並將其儲存為 Outlook 電子郵件 (.eml) 檔案。</span><span class="sxs-lookup"><span data-stu-id="1898c-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="1898c-106">如果您啟用 Microsoft Exchange 整合, 則會將資料封存到 Exchange 存儲區。</span><span class="sxs-lookup"><span data-stu-id="1898c-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="1898c-107">在 Exchange 中封存的資料是可搜尋且可探索的。</span><span class="sxs-lookup"><span data-stu-id="1898c-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="1898c-108">如需存取 Exchange 中已歸檔資料的詳細資訊, 請參閱 Exchange 檔。</span><span class="sxs-lookup"><span data-stu-id="1898c-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1898c-109">使用 Windows PowerShell Cmdlet 匯出存檔資料</span><span class="sxs-lookup"><span data-stu-id="1898c-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1898c-110">您可以使用 Export CSArchivingData Cmdlet 來匯出封存的資料。</span><span class="sxs-lookup"><span data-stu-id="1898c-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="1898c-111">下列命令會將所有寫入的存檔資料匯出至2012年6月1日之後的封存資料庫 atl-sql-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1898c-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="1898c-112">產生的輸出檔案會儲存在資料夾 C:\ArchivingExports。</span><span class="sxs-lookup"><span data-stu-id="1898c-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="1898c-113">下列命令會匯出單一使用者的存檔資料: kenmyer@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1898c-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="1898c-114">這是透過包括 UserUri 參數及使用者的 SIP 位址來完成。</span><span class="sxs-lookup"><span data-stu-id="1898c-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="1898c-115">例如：</span><span class="sxs-lookup"><span data-stu-id="1898c-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="1898c-116">如需詳細資訊, 請參閱[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="1898c-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

