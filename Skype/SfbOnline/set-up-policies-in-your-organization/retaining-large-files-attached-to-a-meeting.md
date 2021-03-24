---
title: 保留附加到商務用 Skype 會議的大型檔案
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
description: 您可以將檔案附加到商務用 Skype 會議，參與者可以開啟並下載。 附加到商務用 Skype 會議的檔案會保留在信箱中，其信箱會置於訴訟保留狀態、已適用 Microsoft 365 或 Office 365 保留原則，或保留與 Microsoft 365 合規性中心電子檔探索案例相關聯的保留狀態。 此內容會儲存到參與者信箱中的可復原專案資料夾。
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100569"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到商務用 Skype 會議的大型檔案

您可以將檔案附加到商務用 Skype 會議，參與者可以開啟並下載。 附加到商務用 Skype 會議的檔案會保留在信箱中，其信箱會置於訴訟保留狀態、已適用 Microsoft 365 或 Office 365 保留原則，或保留與 Microsoft 365 合規性中心電子檔探索案例相關聯的保留狀態。 此內容會儲存到 **參與者信箱中的** 可復原專案資料夾。
  
保留信箱中保留的檔案會編制索引，因此在搜尋參與者的信箱時，可在安全性合規性中心執行內容搜尋時 &amp; 進行搜尋。 不過，大於 30 MB 的附加檔案會分割成兩個或多個較小的檔案，並儲存為壓縮 (.zip) 檔案。 這些  *較小的*  檔案內容不會為搜尋編制索引，而且可能不會在內容搜尋中退回。 不過 *，這些檔案*  的 (例如檔案名和作者) 會編制搜尋索引，並可能在內容搜尋中返回。
  
> [!IMPORTANT]
> Exchange Online 信箱的 MaxReceiveSize 和 MaxSendSize 設定可能會影響從商務用 Skype 會議保留大型檔案的能力。 MaxReceiveSize 和 MaxSendSize 的預設設定分別為 36 MB 和 35 MB。 不過，這些預設設定太小，無法從商務用 Skype 會議保留超過 30 MB 的任何檔案。 這是因為 Exchange Online 使用郵件附件和其他二進位資料的 Base64 編碼。 當郵件編碼時，其大小會增加約 33%。 因此，為了確保保留商務用 Skype 會議的大型檔案，建議您將 MaxReceiveSize 和 MaxSendSize 的值提高至 39 MB (這比先前針對保留使用者解說) 的 30 MB 大小限制大約 33%。 否則，附加到商務用 Skype 會議的大型檔案可能無法保留。 有關在 Exchange Online PowerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令之詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未保留的信箱不會儲存任何會議資料。 例如，在三人會議中，將兩個參與者的信箱標示為保留，會議資料會儲存至這兩個參與者的信箱，但無法儲存到第三個參與者的信箱，因為第三個參與者的信箱並未保留。
  
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點到點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)
  
  
