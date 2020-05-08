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
description: 您可以將檔案附加到商務用 Skype 會議，參與者可以開啟並下載。 附加到商務用 Skype 會議的檔案會保留在任何參與者的信箱中，其信箱是針對訴訟封存進行的，已套用 Microsoft 365 或 Office 365 保留原則，或置於與 Microsoft 365 規範中心中與 eDiscovery 案例相關的保留狀態。 此內容會儲存到其信箱中的參與者 [可復原的專案] 資料夾中。
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164072"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>保留附加到商務用 Skype 會議的大型檔案

您可以將檔案附加到商務用 Skype 會議，參與者可以開啟並下載。 附加到商務用 Skype 會議的檔案會保留在任何參與者的信箱中，其信箱是針對訴訟封存進行的，已套用 Microsoft 365 或 Office 365 保留原則，或置於與 Microsoft 365 規範中心中與 eDiscovery 案例相關的保留狀態。 此內容會儲存到其信箱中的參與者 [可復原的**專案**] 資料夾中。
  
[保留在信箱中的檔案] 是已編制索引，因此可在搜尋參與者信箱時，在安全&amp;規範中心中執行內容搜尋時搜尋。 不過，大於 30 MB 的附加檔案會分割成兩個或更多較小的檔案，並儲存為壓縮（.zip）檔案。 這些較小檔案的*內容*不會編制索引以進行搜尋，而且可能不會在內容搜尋中傳回。 不過，這些檔案的*中繼資料*（例如檔案名和作者）是針對搜尋編制索引，而且可能會在內容搜尋中傳回。
  
> [!IMPORTANT]
> Exchange Online 信箱的 MaxReceiveSize 和 MaxSendSize 設定可能會影響將大型檔案從商務用 Skype 會議中保留的功能。 MaxReceiveSize 和 MaxSendSize 的預設設定分別是 36 MB 和 35 MB。 不過，這些預設設定太小，無法保留超過 30 MB 的商務用 Skype 會議中的任何檔案。 這是因為 Exchange Online 對郵件附件和其他二進位資料使用 Base64 編碼。 當訊息經過編碼時，其大小會增加大約33%。 因此，若要確保保留商務用 Skype 會議的大型檔案，建議您將 MaxReceiveSize 和 MaxSendSize 的值增加至 39 MB （超過先前所述的 30 MB 大小限制的33%），以供處於保留狀態的使用者。 否則，附加到商務用 Skype 會議的大型檔案可能不會保留。 如需使用 Exchange Online PowerShell 中的 [**設定信箱-MaxReceiveSize** ] 和 [**設定信箱] MaxSendSize**命令的詳細資訊，請參閱[設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
未保留的信箱將無法儲存任何會議資料。 例如，在三人的會議中，有兩個參與者的信箱標示為 [保留]，會議資料會儲存至這兩個參與者的信箱，而非第三個參與者的信箱（其信箱未保留）。
  
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[封鎖點對端檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議原則](set-up-conferencing-policies-for-your-organization.md)
  
  
 
