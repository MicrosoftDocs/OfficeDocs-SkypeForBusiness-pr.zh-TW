---
title: 保留附加至會議商務用 Skype檔案
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 您可以將檔案附加到會議商務用 Skype，參與者可以開啟並下載。 附加到 商務用 Skype 會議的檔案會保留在信箱中，其信箱會置於訴訟保留狀態、已適用 Microsoft 365 或 Office 365 保留原則，或置於 Microsoft 365 合規性中心與電子檔探索案例相關聯的保留狀態。 此內容會儲存到參與者信箱中的可復原專案資料夾。
ms.openlocfilehash: 10d793afce0485de749a5609b77f2c769c55fa9d5305a4a815351ef62ff9a8b3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316489"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加至會議商務用 Skype檔案

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

您可以將檔案附加到會議商務用 Skype，參與者可以開啟並下載。 附加到 商務用 Skype 會議的檔案會保留在信箱中，其信箱會置於訴訟保留狀態、已適用 Microsoft 365 或 Office 365 保留原則，或置於 Microsoft 365 合規性中心與電子檔探索案例相關聯的保留狀態。 此內容會儲存到 **參與者信箱中的** 可復原專案資料夾。
  
保留信箱中保留的檔案會編制索引，因此在搜尋參與者的信箱時，可在安全性合規性中心執行內容搜尋時 &amp; 進行搜尋。 不過，大於 30 MB 的附加檔案會分割成兩個或多個較小的檔案，並儲存為壓縮 (.zip) 檔案。 這些  *較小的*  檔案內容不會為搜尋編制索引，而且可能不會在內容搜尋中返回。 不過 *，這些檔案*  的 (例如檔案名和作者) 會編制搜尋索引，並可能在內容搜尋中返回。
  
> [!IMPORTANT]
> 信箱的 MaxReceiveSize 和 MaxSendSize 設定Exchange Online可能會影響從會議保留大型商務用 Skype檔案的能力。 MaxReceiveSize 和 MaxSendSize 的預設設定分別為 36 MB 和 35 MB。 不過，這些預設設定太小，無法保留會議商務用 Skype超過 30 MB 的任何檔案。 這是因為系統Exchange Online郵件附件和其他二進位資料的 Base64 編碼。 當郵件編碼時，其大小會增加約 33%。 因此，為了確保保留 商務用 Skype 會議的大型檔案，建議您將 MaxReceiveSize 和 MaxSendSize 的值提高至 39 MB (這比先前針對保留使用者解說的) 30 MB 大小限制大約 33%。 否則，附加至會議商務用 Skype大型檔案可能不會保留。 有關在 powerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令Exchange Online詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未保留的信箱不會儲存任何會議資料。 例如，在三人會議中，將兩個參與者的信箱標示為保留，會議資料會儲存至這兩個參與者的信箱，但無法儲存到第三個參與者的信箱，因為第三個參與者的信箱並未保留。
  
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點到點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)
  
  
