---
title: 更新 Microsoft Edge 憑證
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
description: 本附錄包含更新 edge 憑證以供小組和商務用 Skype 進行雲端合併的詳細步驟。
ms.openlocfilehash: 724ac63239c881283368fbd617ce0654d49fc0e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120342"
---
# <a name="update-the-edge-certificate"></a><span data-ttu-id="0934a-103">更新 Microsoft Edge 憑證</span><span class="sxs-lookup"><span data-stu-id="0934a-103">Update the edge certificate</span></span>

<span data-ttu-id="0934a-104">更新 edge 憑證是重要步驟，可確保具有 SipDomain1 的部署環境可以加入雲端環境與 SipDomain2，並確保在共用位址空間環境中正確地路由傳送到兩個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="0934a-104">Updating the edge certificate is the key step to ensuring that an on-prem environment with SipDomain1 can join a cloud environment with SipDomain2 and ensure proper routing in a shared address space environment across the two SIP domains.</span></span> <span data-ttu-id="0934a-105">如需執行此步驟的內容，請參閱 [Cloud 整合中針對團隊和商務用 Skype](cloud-consolidation.md) 的步驟14。</span><span class="sxs-lookup"><span data-stu-id="0934a-105">See step 14 in [Cloud consolidation for Teams and Skype for Business](cloud-consolidation.md) for context in which you might perform this step.</span></span> <span data-ttu-id="0934a-106">在我們的範例中，SipDomain1 是 AcquiredCompany。 <span>com 和 SipDomain2 為 OriginalCompany。 <span>Com。</span><span class="sxs-lookup"><span data-stu-id="0934a-106">In our examples, SipDomain1 is AcquiredCompany.<span>com and SipDomain2 is OriginalCompany.<span>com.</span></span>

<span data-ttu-id="0934a-107">在內部部署環境中，所有 edge server 上的主體替代名稱 (的憑證) 必須更新，以包含存在於純線上承租人中的所有 SIP 網域 (排除任何 name.onmicrosoft.com17。 <span>com 網域) ，格式為 "sip \<domain> "。</span><span class="sxs-lookup"><span data-stu-id="0934a-107">The subject alternate name (SAN) of the certificate on all edge servers in the on-premises environment must be updated to include all SIP domains that exist in the pure online tenant (excluding any onmicrosoft.<span>com domains), in the form “sip.\<domain>”.</span></span>  <span data-ttu-id="0934a-108">在我們的範例中，這是 sip。OriginalCompany。 <span>Com。</span><span class="sxs-lookup"><span data-stu-id="0934a-108">In our example, this is sip.OriginalCompany.<span>com.</span></span> <span data-ttu-id="0934a-109">在將任何使用者遷移至雲端之前，這是非常重要的步驟。</span><span class="sxs-lookup"><span data-stu-id="0934a-109">This step is critical to do before migrating any users to the cloud.</span></span>

<span data-ttu-id="0934a-110">**步驟：**</span><span class="sxs-lookup"><span data-stu-id="0934a-110">**Steps:**</span></span>

1.  <span data-ttu-id="0934a-111">針對雲端環境中的所有 SIP 網域，取得現有的現有專案和 SAN 中的其他專案的新外部 Edge 憑證 (包含) "SIP" 的 onmicrosoft.com 網域 <DomainName> 。</span><span class="sxs-lookup"><span data-stu-id="0934a-111">Obtain a new External Edge certificate for the edge that has all existing entries plus additional entries in the SAN for all SIP domains in the cloud environment (excluding \*.onmicrosoft.com domains) in the form “sip.<DomainName>”.</span></span>
2.  <span data-ttu-id="0934a-112">在每一部 edge server 上以本機方式安裝憑證，並將它指派給每個 edge service 上的 Skype Edge service。</span><span class="sxs-lookup"><span data-stu-id="0934a-112">Install the certificate locally on each edge server and assign it to the Skype Edge service on each of the edge service.</span></span>  <span data-ttu-id="0934a-113">如需詳細步驟，請參閱 [Deploy Edge Service In 商務用 Skype Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)中的「外部 Edge interface 憑證」一節。</span><span class="sxs-lookup"><span data-stu-id="0934a-113">For detailed steps, see the section “External Edge interface certificates” in [Deploy Edge Service in Skype for Business Server 2015](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md).</span></span>
3.  <span data-ttu-id="0934a-114">在每一部 Edge server 上重新開機 Edge service。</span><span class="sxs-lookup"><span data-stu-id="0934a-114">Restart the Edge service on each of the edge servers.</span></span> <span data-ttu-id="0934a-115">您可以使用下列 PowerShell 命令，在單一方塊中執行這項操作：</span><span class="sxs-lookup"><span data-stu-id="0934a-115">You can do this for a single box with the following PowerShell commands:</span></span>

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a><span data-ttu-id="0934a-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0934a-116">See also</span></span>

[<span data-ttu-id="0934a-117">小組和商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="0934a-117">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)