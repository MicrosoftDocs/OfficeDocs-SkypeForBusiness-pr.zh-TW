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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附錄包含更新 edge 憑證的詳細步驟, 做為小組和商務用 Skype 的雲端合併的一部分。
ms.openlocfilehash: 1c3aaa8859db530ceccbebc68ae76f21e8d4a77f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185500"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="46237-103">更新邊緣憑證</span><span class="sxs-lookup"><span data-stu-id="46237-103">Update the edge certificate</span></span>

<span data-ttu-id="46237-104">更新 edge 憑證是主要步驟, 可確保 SipDomain1 的內部部署環境可以使用 SipDomain2 加入雲端環境, 並確保透過兩個 SIP 網域在共用位址空間環境中正確路由。</span><span class="sxs-lookup"><span data-stu-id="46237-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="46237-105">請參閱適用于[團隊與商務用 Skype 之雲端整合](cloud-consolidation.md)中的步驟 14, 以取得您可能會執行此步驟的內容。</span><span class="sxs-lookup"><span data-stu-id="46237-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="46237-106">在我們的範例中, SipDomain1 是 AcquiredCompany。<span>Com 和 SipDomain2 是 OriginalCompany。<span>com。</span><span class="sxs-lookup"><span data-stu-id="46237-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="46237-107">在內部部署環境中, 所有邊緣伺服器上的憑證的主體替換名稱 (SAN) 都必須更新, 才能包含純粹線上租使用者中存在的所有 SIP 網域 (不包括任何 onmicrosoft<span> )。com 網域), 其形式為「sip。\<網域> "。</span><span class="sxs-lookup"><span data-stu-id="46237-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="46237-108">在我們的範例中, 這是 sip。OriginalCompany.<span>com。</span><span class="sxs-lookup"><span data-stu-id="46237-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="46237-109">在將任何使用者移植到雲端之前, 必須先執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="46237-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="46237-110">**步驟**</span><span class="sxs-lookup"><span data-stu-id="46237-110">**Steps:**</span></span>

1.  <span data-ttu-id="46237-111">針對雲端環境中的所有 SIP 網域 (不包括 \*. onmicrosoft.com domain), 以「sip」形式取得所有現有專案的邊緣的新外部邊緣憑證, 以及 SAN 中所有 SIP 網域的 SAN 中的其他專案。<DomainName>"。</span><span class="sxs-lookup"><span data-stu-id="46237-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="46237-112">在每個 edge 伺服器上本機安裝證書, 並將它指派給每個 edge 服務上的 Skype Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="46237-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="46237-113">如需詳細步驟, 請參閱[商務用 Skype Server 2015 的部署邊緣服務](https://technet.microsoft.com/en-us/library/dn951368.aspx)中的「外部邊緣介面憑證」一節。</span><span class="sxs-lookup"><span data-stu-id="46237-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/dn951368.aspx).</span></span>
3.  <span data-ttu-id="46237-114">在每個邊緣伺服器上重新開機 Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="46237-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="46237-115">您可以針對單一方塊執行下列 PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="46237-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="46237-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="46237-116">See also</span></span>

[<span data-ttu-id="46237-117">團隊與商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="46237-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)