---
title: 商務用 Skype Server 中的分支網站 SIP 中繼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: 瞭解商務用 Skype Server Enterprise Voice 中分支網站的 SIP 中繼。
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803253"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="9c4e8-103">商務用 Skype Server 中的分支網站 SIP 中繼</span><span class="sxs-lookup"><span data-stu-id="9c4e8-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="9c4e8-104">瞭解商務用 Skype Server Enterprise Voice 中分支網站的 SIP 中繼。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9c4e8-105">在某些情況下，您可能需要在選取的分支網站上執行分散式 SIP 中繼。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="9c4e8-106">若要判斷分支網站是否需要 SIP 幹線，以及有關在分支網站中部署 SIP trunks 之支援拓撲選項的詳細資訊，請參閱[商務用 Skype 伺服器中的 sip 中繼](sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="9c4e8-107">分支網站 SIP 中繼需求分析範例</span><span class="sxs-lookup"><span data-stu-id="9c4e8-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="9c4e8-108">當您決定要部署分支網站 SIP 幹線時，您必須執行特定網站的成本分析。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="9c4e8-109">例如，在雷蒙德、華盛頓及紐約的分支網站中有中央網站的企業，都應該進行分析，判斷是否要將 SIP 主幹從紐約網站實施到本機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="9c4e8-110">若要判斷位於紐約的分散式 SIP 主幹是否經濟高效，請找出哪個直接撥入式撥號（已有）號碼將使用 SIP 幹線，並分析紐約的呼叫次數，而不是雷德蒙者（425）。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="9c4e8-111">您可以在中央網站上終止分支網站。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="9c4e8-112">例如，雷德蒙的中央網站可以主持紐約分支網站的編號。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="9c4e8-113">如果實施分散式 SIP 幹線的成本低於這些通話的成本，請考慮在紐約分支網站實施 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="9c4e8-114">其他分支網站 SIP 幹線需求</span><span class="sxs-lookup"><span data-stu-id="9c4e8-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="9c4e8-115">在部署 SIP 幹線（而不是閘道）之間選擇，就會根據每個選項的公用交換電話網絡（PSTN）長途電話費用之間的差異而定。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="9c4e8-116">如果您部署分支網站 SIP 幹線，您也必須判斷復原能力和頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="9c4e8-117">如果您分支網站與中央網站之間的連結有彈性且頻寬充足，您可以部署 SIP 主幹或閘道。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="9c4e8-118">您不需要在分支網站上部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="9c4e8-119">如果您分支網站與中央網站之間的連結沒有復原能力，請部署 Survivable 分支裝置，或使用分支網站上的閘道或 SIP 幹線來部署 Survivable 分支伺服器。</span><span class="sxs-lookup"><span data-stu-id="9c4e8-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

