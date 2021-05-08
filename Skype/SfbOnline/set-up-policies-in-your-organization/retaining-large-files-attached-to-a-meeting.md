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
description: 您可以將檔案附加至商務用 Skype，參與者可以開啟並下載。 附加到 商務用 Skype 會議的檔案會保留在信箱中，其信箱會置於訴訟保留狀態、已適用 Microsoft 365 或 Office 365 保留原則，或置於 Microsoft 365 合規性中心與電子檔探索案例相關聯的保留狀態。 此內容會儲存到參與者信箱中的可復原專案資料夾。
ms.openlocfilehash: 74605b9aebf6d83619282d9cfc9094216d2fe6f1
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240105"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="aab0d-105">保留附加至會議商務用 Skype檔案</span><span class="sxs-lookup"><span data-stu-id="aab0d-105">Retaining large files attached to a Skype for Business meeting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="aab0d-106">您可以將檔案附加至商務用 Skype，參與者可以開啟並下載。</span><span class="sxs-lookup"><span data-stu-id="aab0d-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="aab0d-107">附加到 商務用 Skype 會議的檔案會保留在信箱中，其信箱會置於訴訟保留狀態、已適用 Microsoft 365 或 Office 365 保留原則，或置於 Microsoft 365 合規性中心與電子檔探索案例相關聯的保留狀態。</span><span class="sxs-lookup"><span data-stu-id="aab0d-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="aab0d-108">此內容會儲存到 **參與者信箱中的** 可復原專案資料夾。</span><span class="sxs-lookup"><span data-stu-id="aab0d-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="aab0d-109">保留信箱中保留的檔案會編制索引，因此在搜尋參與者的信箱時，可在安全性合規性中心執行內容搜尋時 &amp; 進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="aab0d-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="aab0d-110">不過，大於 30 MB 的附加檔案會分割成兩個或多個較小的檔案，並儲存為壓縮 (.zip) 檔案。</span><span class="sxs-lookup"><span data-stu-id="aab0d-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="aab0d-111">這些  *較小的*  檔案內容不會為搜尋編制索引，而且可能不會在內容搜尋中返回。</span><span class="sxs-lookup"><span data-stu-id="aab0d-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="aab0d-112">不過 *，這些檔案*  的 (例如檔案名和作者) 會編制搜尋索引，並可能在內容搜尋中返回。</span><span class="sxs-lookup"><span data-stu-id="aab0d-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aab0d-113">信箱的 MaxReceiveSize 和 MaxSendSize 設定Exchange Online可能會影響從會議保留大型商務用 Skype檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="aab0d-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="aab0d-114">MaxReceiveSize 和 MaxSendSize 的預設設定分別為 36 MB 和 35 MB。</span><span class="sxs-lookup"><span data-stu-id="aab0d-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="aab0d-115">不過，這些預設設定太小，無法保留會議商務用 Skype超過 30 MB 的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="aab0d-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="aab0d-116">這是因為系統Exchange Online郵件附件和其他二進位資料的 Base64 編碼。</span><span class="sxs-lookup"><span data-stu-id="aab0d-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="aab0d-117">當郵件編碼時，其大小會增加約 33%。</span><span class="sxs-lookup"><span data-stu-id="aab0d-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="aab0d-118">因此，為了確保保留 商務用 Skype 會議的大型檔案，建議您將 MaxReceiveSize 和 MaxSendSize 的值提高至 39 MB (這比先前針對保留使用者解說) 所說明的 30 MB 大小限制大約 33%。</span><span class="sxs-lookup"><span data-stu-id="aab0d-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="aab0d-119">否則，附加至會議商務用 Skype大型檔案可能不會保留。</span><span class="sxs-lookup"><span data-stu-id="aab0d-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="aab0d-120">有關在 PowerShell 中使用 **Set-Mailbox -MaxReceiveSize** 和 **Set-Mailbox -MaxSendSize** 命令Exchange Online，請參閱 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)。</span><span class="sxs-lookup"><span data-stu-id="aab0d-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="aab0d-121">未保留的信箱不會儲存任何會議資料。</span><span class="sxs-lookup"><span data-stu-id="aab0d-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="aab0d-122">例如，在三人會議中，將兩個參與者的信箱標示為保留，會議資料會儲存至這兩個參與者的信箱，但無法儲存到第三個參與者的信箱，因為第三個參與者的信箱並未保留。</span><span class="sxs-lookup"><span data-stu-id="aab0d-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="aab0d-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="aab0d-123">Related topics</span></span>
[<span data-ttu-id="aab0d-124">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="aab0d-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="aab0d-125">封鎖點到點檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="aab0d-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="aab0d-126">設定組織的用戶端原則</span><span class="sxs-lookup"><span data-stu-id="aab0d-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="aab0d-127">在組織中設定會議策略</span><span class="sxs-lookup"><span data-stu-id="aab0d-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
