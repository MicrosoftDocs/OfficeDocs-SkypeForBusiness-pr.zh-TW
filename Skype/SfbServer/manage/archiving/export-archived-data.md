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
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817563"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>在商務用 Skype Server 中匯出封存的資料

**摘要：** 瞭解如何匯出商務用 Skype 伺服器的封存資料。
  
封存資料庫中封存的資料無法以可讀取的格式進行搜尋，但是您可以使用 **Export-CsArchivingData** Cmdlet 從資料庫提取記錄，並將其儲存為 Outlook 電子郵件 (.eml) 檔案。
  
如果您啟用 Microsoft Exchange 整合，資料會封存在 Exchange 存放區中。 Exchange 中封存的資料是可搜尋且可探索的。 如需存取 Exchange 中已封存資料的詳細資訊，請參閱 Exchange 檔。
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 匯出封存資料

您可以使用 Export-CSArchivingData Cmdlet 來匯出封存的資料。 
  
下列命令會匯出從2012年6月1日起寫入封存資料庫 atl-sql-001.contoso.com 的所有封存資料。 所產生的輸出檔案會儲存在 C:\ArchivingExports 資料夾中。
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

下列命令會匯出單一使用者的封存資料： kenmyer@contoso.com。 若要執行此操作，您可以加入 UserUri 參數後接使用者的 SIP 位址。 例如： 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

如需詳細資訊，請參閱 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) Cmdlet 的 [說明] 主題。
  

