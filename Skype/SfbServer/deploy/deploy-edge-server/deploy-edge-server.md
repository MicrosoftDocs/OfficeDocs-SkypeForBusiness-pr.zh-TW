---
title: 在商務用 Skype Server 中部署 Edge 伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '摘要: 瞭解如何將 Edge 伺服器或邊緣池部署到您的商務用 Skype Server 環境中。'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193893"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="09e63-103">在商務用 Skype Server 中部署 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="09e63-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="09e63-104">**摘要:** 瞭解如何將邊緣伺服器或邊緣池部署到您的商務用 Skype Server 環境中。</span><span class="sxs-lookup"><span data-stu-id="09e63-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="09e63-105">為什麼要將 Edge 伺服器或邊緣池部署到商務用 Skype Server 環境中？</span><span class="sxs-lookup"><span data-stu-id="09e63-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="09e63-106">如果您需要未登入貴組織內部網路的外部使用者, 才能與內部使用者互動, 就必須這麼做。</span><span class="sxs-lookup"><span data-stu-id="09e63-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="09e63-107">這些外部使用者可以經過驗證與匿名遠端使用者、聯盟夥伴或其他行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="09e63-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="09e63-108">商務用 Skype Server 的邊緣部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="09e63-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="09e63-109">如上所述, 在商務用 Skype Server 的 Edge 伺服器部署中, 有大量的情況。</span><span class="sxs-lookup"><span data-stu-id="09e63-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="09e63-110">此檢查清單可讓您大致瞭解您需要執行的工作, 以及更詳細的步驟連結。</span><span class="sxs-lookup"><span data-stu-id="09e63-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="09e63-111">我們希望您已開始在[商務用 Skype server 區段規劃中進行 Edge 伺服器部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="09e63-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="09e63-112">如果不是, 我們所參照的許多專案都會在該處詳細說明。</span><span class="sxs-lookup"><span data-stu-id="09e63-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="09e63-113">[部署] 區段只包含程式, 所以如果您想要瞭解這些步驟背後的理由, 請開始進行規劃。</span><span class="sxs-lookup"><span data-stu-id="09e63-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="09e63-114">本檔也假設您也已完成商務用 Skype Server 的基本部署。</span><span class="sxs-lookup"><span data-stu-id="09e63-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="09e63-115">您可能會與邊緣並排進行部署, 但您必須先執行這些步驟, 然後才能針對此處所述的邊緣來變更拓撲的變更。</span><span class="sxs-lookup"><span data-stu-id="09e63-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="09e63-116">這些是您需要追蹤的高層步驟, 而您可以找到以下步驟:</span><span class="sxs-lookup"><span data-stu-id="09e63-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="09e63-117">商務用 Skype Server 中的邊緣伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="09e63-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="09e63-118">商務用 Skype Server 中的邊緣伺服器環境需求</span><span class="sxs-lookup"><span data-stu-id="09e63-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="09e63-119">為商務用 Skype Server 建立邊緣拓撲</span><span class="sxs-lookup"><span data-stu-id="09e63-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="09e63-120">在商務用 Skype Server 中部署邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="09e63-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="09e63-121">驗證您在商務用 Skype Server 中的邊緣部署</span><span class="sxs-lookup"><span data-stu-id="09e63-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

