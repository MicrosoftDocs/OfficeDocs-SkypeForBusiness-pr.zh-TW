---
title: 在商務用 Skype Server 中部署 Edge Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 摘要：瞭解如何在商務用 Skype 伺服器環境中部署 Edge Server 或 Edge 集區。
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804383"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="37d08-103">在商務用 Skype Server 中部署 Edge Server</span><span class="sxs-lookup"><span data-stu-id="37d08-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="37d08-104">**摘要：** 瞭解如何在商務用 Skype 伺服器環境中部署 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="37d08-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="37d08-105">為什麼要將 Edge Server 或 Edge 集區部署到商務用 Skype Server 環境中？</span><span class="sxs-lookup"><span data-stu-id="37d08-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="37d08-106">如果您需要未登入組織內部網路的外部使用者才能與內部使用者互動，則必須使用此方式。</span><span class="sxs-lookup"><span data-stu-id="37d08-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="37d08-107">這些外部使用者可能會經過驗證和匿名遠端使用者、同盟合作夥伴或其他行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="37d08-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="37d08-108">商務用 Skype Server Edge 的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="37d08-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="37d08-109">如以上所述，大量的商務用 Skype Server 部署會進入 Edge Server 部署。</span><span class="sxs-lookup"><span data-stu-id="37d08-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="37d08-110">這個檢查清單可讓您瞭解所需執行的工作，以及更詳細的步驟。</span><span class="sxs-lookup"><span data-stu-id="37d08-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="37d08-111">我們希望您已開始在 [商務用 Skype server 中規劃 Edge server 部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) 一節。</span><span class="sxs-lookup"><span data-stu-id="37d08-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="37d08-112">否則，我們所指的許多事情都會在這裡詳述。</span><span class="sxs-lookup"><span data-stu-id="37d08-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="37d08-113">[部署] 區段只包含程式，因此，如果您想知道這些步驟的執行原因，規劃是開始的地方。</span><span class="sxs-lookup"><span data-stu-id="37d08-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="37d08-114">本檔也會假設您已完成商務用 Skype Server 的基本部署。</span><span class="sxs-lookup"><span data-stu-id="37d08-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="37d08-115">您可以使用 Edge 進行部署，但您必須先遵循這些步驟，然後才能夠對這裡所述的 Edge 進行拓撲變更。。）。</span><span class="sxs-lookup"><span data-stu-id="37d08-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="37d08-116">以下是您將需要遵循的高階步驟，以及您將會發現這些步驟的位置：</span><span class="sxs-lookup"><span data-stu-id="37d08-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="37d08-117">商務用 Skype Server 中的 Edge Server 系統需求</span><span class="sxs-lookup"><span data-stu-id="37d08-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="37d08-118">商務用 Skype Server 中的 Edge Server 環境需求</span><span class="sxs-lookup"><span data-stu-id="37d08-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="37d08-119">為商務用 Skype Server 建立 Edge 拓撲</span><span class="sxs-lookup"><span data-stu-id="37d08-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="37d08-120">在商務用 Skype Server 中部署 Edge Server</span><span class="sxs-lookup"><span data-stu-id="37d08-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="37d08-121">在商務用 Skype Server 中驗證 Edge 部署</span><span class="sxs-lookup"><span data-stu-id="37d08-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

