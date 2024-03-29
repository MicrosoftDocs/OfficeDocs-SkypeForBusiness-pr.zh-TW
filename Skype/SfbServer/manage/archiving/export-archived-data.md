---
title: 匯出商務用 Skype Server 中的封存資料
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 摘要：瞭解如何匯出商務用 Skype Server 的封存資料。
ms.openlocfilehash: d31d1abb5d4c194b891cf4c45a38f723e5ea2d4b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402957"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>匯出商務用 Skype Server 中的封存資料

**總結：** 瞭解如何匯出商務用 Skype Server 的封存資料。
  
封存資料庫中封存的資料無法以可讀取的格式進行搜尋，但是您可以使用 **Export-CsArchivingData** Cmdlet 從資料庫中解壓縮記錄，並將其儲存為 Outlook 的電子郵件 (.eml) 檔案。
  
如果您啟用 Microsoft Exchange 整合，資料會封存 Exchange 存放區中。 在 Exchange 中封存的資料可供搜尋和探索。 如需存取 Exchange 中封存之資料的詳細資訊，請參閱 Exchange 檔。
  
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

如需詳細資訊，請參閱 [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) Cmdlet 的 [說明] 主題。
