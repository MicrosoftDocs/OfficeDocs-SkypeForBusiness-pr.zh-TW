---
title: 更新邊緣憑證
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附錄包含 microsoft Teams 和商務用 Skype 雲端合併彙算的過程中更新邊緣憑證的詳細的步驟。
ms.openlocfilehash: 3e6b151e340a0942b561edd2233795fad94c3a9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888602"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="4d61f-103">更新邊緣憑證</span><span class="sxs-lookup"><span data-stu-id="4d61f-103">Update the edge certificate</span></span>

<span data-ttu-id="4d61f-104">更新邊緣憑證是重要步驟，確保 SipDomain1 與內部部署環境可以加入 SipDomain2 的雲端環境，並確保跨兩個 SIP 網域共用的位址空間環境中適當路由。</span><span class="sxs-lookup"><span data-stu-id="4d61f-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="4d61f-105">請參閱中的步驟 14[雲端彙總針對小組與商務用 Skype](cloud-consolidation.md)內容中，您可能會執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="4d61f-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="4d61f-106">在我們的範例，SipDomain1 是 AcquiredCompany。<span>com 和 SipDomain2 是 OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="4d61f-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="4d61f-107">必須更新內部部署環境中的所有 edge server 上的憑證的主體替代名稱 (SAN)，以包括單純的線上租用戶中存在的所有 SIP 網域 (不含任何 onmicrosoft。<span>com 網域），格式為 「 sip。\<網域> 」。</span><span class="sxs-lookup"><span data-stu-id="4d61f-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="4d61f-108">在我們的範例，這是 sip。OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="4d61f-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="4d61f-109">此步驟是關鍵移轉至雲端的任何使用者之前執行。</span><span class="sxs-lookup"><span data-stu-id="4d61f-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="4d61f-110">**步驟：**</span><span class="sxs-lookup"><span data-stu-id="4d61f-110">**Steps:**</span></span>

1.  <span data-ttu-id="4d61f-111">取得新的外部邊緣憑證邊緣具有雲端環境中的所有 SIP 網域在 SAN 中的所有現有項目加上額外的項目 (不含 \*。 onmicrosoft.com 網域) 中的表單 」 sip。<DomainName>"。</span><span class="sxs-lookup"><span data-stu-id="4d61f-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="4d61f-112">將憑證安裝在本機上每部 edge server，並將其指派給每個 edge service 的 Skype Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="4d61f-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="4d61f-113">如需詳細步驟，請參閱[在商務用 Skype Server 2015 中部署 Edge Service](https://technet.microsoft.com/library/dn951368.aspx)中的 「 外部 Edge 介面的憑證 」 一節。</span><span class="sxs-lookup"><span data-stu-id="4d61f-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="4d61f-114">重新啟動每一部 edge server 上的 [Edge service。</span><span class="sxs-lookup"><span data-stu-id="4d61f-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="4d61f-115">您可以針對單一] 方塊中，使用下列 PowerShell 命令來這麼做：</span><span class="sxs-lookup"><span data-stu-id="4d61f-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="4d61f-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4d61f-116">See also</span></span>

[<span data-ttu-id="4d61f-117">針對小組與 Skype for Business 的雲端彙總</span><span class="sxs-lookup"><span data-stu-id="4d61f-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)