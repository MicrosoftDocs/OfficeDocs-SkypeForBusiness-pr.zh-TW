---
title: 在商務用 Skype Server 中匯出已歸檔的資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要：瞭解如何匯出商務用 Skype Server 的存檔資料。
ms.openlocfilehash: 12ba59ff11a988fd95eb2207cd826a4399db2779
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818905"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>在商務用 Skype Server 中匯出已歸檔的資料

**摘要：** 瞭解如何匯出商務用 Skype Server 的存檔資料。
  
歸檔資料庫中封存的資料無法以可讀取的格式進行搜尋，但您可以使用**Export CsArchivingData** Cmdlet 來從資料庫提取記錄，並將其儲存為 Outlook 電子郵件（.eml）檔案。
  
如果您啟用 Microsoft Exchange 整合，則會將資料封存到 Exchange 存儲區。 在 Exchange 中封存的資料是可搜尋且可探索的。 如需存取 Exchange 中已歸檔資料的詳細資訊，請參閱 Exchange 檔。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 匯出存檔資料

您可以使用 Export CSArchivingData Cmdlet 來匯出封存的資料。 
  
下列命令會將所有寫入的存檔資料匯出至2012年6月1日之後的封存資料庫 atl-sql-001.contoso.com。 產生的輸出檔案會儲存在資料夾 C:\ArchivingExports。
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

下列命令會匯出單一使用者的存檔資料： kenmyer@contoso.com。 這是透過包括 UserUri 參數及使用者的 SIP 位址來完成。 例如： 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

如需詳細資訊，請參閱[Export CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) Cmdlet 的說明主題。
  

