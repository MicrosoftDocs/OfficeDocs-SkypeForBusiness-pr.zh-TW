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
f1keywords: None
ms.custom:
- Setup
description: 您可以將檔案附加到商務用 Skype 會議，參與者可以開啟並下載。 附加到商務用 Skype 會議的檔案會保留在任何參與者的信箱中，其信箱是在訴訟封存中，已套用 Office 365 保留原則，或是放在與 Office 365 安全性中與 eDiscovery 案例相關的保留中&amp;合規性中心。 此內容會儲存到其信箱中的參與者 [可復原的專案] 資料夾中。
ms.openlocfilehash: 4a8022b522f933ff8897586f632764eda77c6a67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642677"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="ee2ed-105">保留附加到商務用 Skype 會議的大型檔案</span><span class="sxs-lookup"><span data-stu-id="ee2ed-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="ee2ed-106">您可以將檔案附加到商務用 Skype 會議，參與者可以開啟並下載。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="ee2ed-107">附加到商務用 Skype 會議的檔案會保留在任何參與者的信箱中，其信箱是在訴訟封存中，已套用 Office 365 保留原則，或是放在與 Office 365 安全性中與 eDiscovery 案例相關的保留中&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="ee2ed-108">此內容會儲存到其信箱中的參與者 [可復原的**專案**] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="ee2ed-109">[保留在信箱中的檔案] 是已編制索引，因此可在搜尋參與者信箱時，在安全&amp;規範中心中執行內容搜尋時搜尋。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="ee2ed-110">不過，大於 30 MB 的附加檔案會分割成兩個或更多較小的檔案，並儲存為壓縮（.zip）檔案。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="ee2ed-111">這些較小檔案的*內容*不會編制索引以進行搜尋，而且可能不會在內容搜尋中傳回。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="ee2ed-112">不過，這些檔案的*中繼資料*（例如檔案名和作者）是針對搜尋編制索引，而且可能會在內容搜尋中傳回。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ee2ed-113">Exchange Online 信箱的 MaxReceiveSize 和 MaxSendSize 設定可能會影響將大型檔案從商務用 Skype 會議中保留的功能。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="ee2ed-114">MaxReceiveSize 和 MaxSendSize 的預設設定分別是 36 MB 和 35 MB。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="ee2ed-115">不過，這些預設設定太小，無法保留超過 30 MB 的商務用 Skype 會議中的任何檔案。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="ee2ed-116">這是因為 Exchange Online 對郵件附件和其他二進位資料使用 Base64 編碼。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="ee2ed-117">當訊息經過編碼時，其大小會增加大約33%。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="ee2ed-118">因此，若要確保保留商務用 Skype 會議的大型檔案，建議您將 MaxReceiveSize 和 MaxSendSize 的值增加至 39 MB （大約比先前所述的 30 MB 大小限制還要大33%）針對處於保留狀態的使用者。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="ee2ed-119">否則，附加到商務用 Skype 會議的大型檔案可能不會保留。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="ee2ed-120">如需使用 Exchange Online PowerShell 中的 [**設定信箱-MaxReceiveSize** ] 和 [**設定信箱] MaxSendSize**命令的詳細資訊，請參閱[設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="ee2ed-121">未保留的信箱將無法儲存任何會議資料。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="ee2ed-122">例如，在三人的會議中，有兩個參與者的信箱標示為 [保留]，會議資料會儲存至這兩個參與者的信箱，而非第三個參與者的信箱（其信箱未保留）。</span><span class="sxs-lookup"><span data-stu-id="ee2ed-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ee2ed-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee2ed-123">Related topics</span></span>
[<span data-ttu-id="ee2ed-124">建立自訂外部存取原則</span><span class="sxs-lookup"><span data-stu-id="ee2ed-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="ee2ed-125">封鎖點對端檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="ee2ed-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ee2ed-126">為您的組織設定用戶端原則</span><span class="sxs-lookup"><span data-stu-id="ee2ed-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="ee2ed-127">在組織中設定會議原則</span><span class="sxs-lookup"><span data-stu-id="ee2ed-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 