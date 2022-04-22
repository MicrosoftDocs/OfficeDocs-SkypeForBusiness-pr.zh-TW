---
title: 保留附加至商務用 Skype會議的大型檔案
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, v-tophillips
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 您可以將檔案附加至商務用 Skype會議，參與者就可以開啟並下載。 附加至商務用 Skype會議的檔案會保留在任何參與者的信箱中，該參與者的信箱設為訴訟資料暫留、已套用Microsoft 365或Office 365保留原則，或是在 Microsoft Purview 合規性入口網站中將電子檔探索案例相關聯的保留狀態。 此內容會儲存到參與者信箱中的 [可復原的專案] 資料夾。
ms.openlocfilehash: b799c1a471ac3884aa1b22cc1a681e53ee8284e9
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031868"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加至商務用 Skype會議的大型檔案

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

您可以將檔案附加至商務用 Skype會議，參與者就可以開啟並下載。 附加至商務用 Skype會議的檔案會保留在任何參與者的信箱中，該參與者的信箱設為訴訟資料暫留、已套用Microsoft 365或Office 365保留原則，或是在 Microsoft Purview 合規性入口網站中將電子檔探索案例相關聯的保留狀態。 此內容會儲存到參與者信箱中的 **[可復原的專案** ] 資料夾。
  
保留信箱中的檔案會編制索引，因此在安全性合規性中心執行 &amp; 內容搜尋時，可以在搜尋參與者的信箱時進行搜尋。 不過，大於 30 MB 的附加檔案會分割成兩個或多個較小的檔案，並儲存為壓縮的 (.zip) 檔案。 這些較小的檔案  *內容*  不會編制搜尋索引，可能不會在內容搜尋中傳回。 不過，這些檔案的 *中繼資料*  (例如檔案名和作者) 會編制搜尋索引，並可能會在內容搜尋中傳回。
  
> [!IMPORTANT]
> Exchange Online信箱的 MaxReceiveSize 和 MaxSendSize 設定可能會影響保留商務用 Skype會議中大型檔案的能力。 MaxReceiveSize 和 MaxSendSize 的預設設定分別為 36 MB 和 35 MB。 不過，這些預設設定太小，無法保留商務用 Skype會議中大於 30 MB 的任何檔案。 這是因為Exchange Online使用郵件附件和其他二進位資料的 Base64 編碼。 當郵件編碼時，其大小會增加約 33%。 因此，為了確保保留商務用 Skype會議中的大型檔案，建議您將 MaxReceiveSize 和 MaxSendSize 的值增加到 39 MB (比先前針對被保留狀態的使用者所說明) 所述的 30 MB 大小限制大約 33%。 否則，附加至商務用 Skype會議的大型檔案可能不會保留。 如需在 Exchange Online PowerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令的詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未保留的信箱不會儲存任何會議資料。 例如，在已標示兩個參與者信箱保留的三人會議中，會議資料會儲存至這兩個參與者的信箱，但不會儲存至第三位參與者的信箱，而該參與者的信箱並未保留該信箱。
  
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點對點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在貴組織中設定會議原則](set-up-conferencing-policies-for-your-organization.md)
  
  
