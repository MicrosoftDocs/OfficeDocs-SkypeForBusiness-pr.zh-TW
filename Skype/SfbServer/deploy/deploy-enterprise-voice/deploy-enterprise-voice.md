---
title: 在商務用 Skype Server 中部署企業語音
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 摘要：瞭解如何在中央網站上部署商務用 Skype Server 的 Enterprise Voice。
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812493"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="6143e-103">在商務用 Skype Server 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="6143e-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="6143e-104">**摘要：** 瞭解如何在中央網站上部署商務用 Skype Server 的 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="6143e-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="6143e-105">使用本主題在中央網站部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="6143e-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="6143e-106">若要在分支網站部署企業語音，請跳過 [部署分支網站](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6143e-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="6143e-107">本節包含在每一部前端伺服器或 Standard Edition server 上組合轉送伺服器的部署程式，如建議，也適用于具備獨立轉送伺服器集區的部署。如果您使用拓撲產生器來定義及發行每一部前端伺服器或 Standard Edition server 上的轉送伺服器的拓撲，您可以略過下列內容，因為當您為前端伺服器集區或 Standard Edition server 安裝檔時，部署嚮導已自動安裝轉送伺服器的檔案：</span><span class="sxs-lookup"><span data-stu-id="6143e-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="6143e-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="6143e-108">In this section</span></span>

- [<span data-ttu-id="6143e-109">商務用 Skype Server 中的 Enterprise Voice 安全性和設定先決條件</span><span class="sxs-lookup"><span data-stu-id="6143e-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="6143e-110">在商務用 Skype Server 中的拓撲產生器中部署轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="6143e-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="6143e-111">在商務用 Skype Server 的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="6143e-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="6143e-112">在商務用 Skype Server 中定義拓撲產生器中的其他主幹</span><span class="sxs-lookup"><span data-stu-id="6143e-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="6143e-113">在商務用 Skype Server 中安裝轉送伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="6143e-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="6143e-114">在商務用 Skype Server 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="6143e-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="6143e-115">在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="6143e-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="6143e-116">在商務用 Skype Server 中建立或修改呼叫識別碼簡報的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="6143e-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="6143e-117">在商務用 Skype 中建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="6143e-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="6143e-118">在商務用 Skype Server 中建立或修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="6143e-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="6143e-119">在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="6143e-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="6143e-120">在商務用 Skype Server 中啟用使用者的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6143e-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="6143e-121">在商務用 Skype Server 中部署 advanced Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="6143e-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="6143e-122">在商務用 Skype 中部署通話管理功能</span><span class="sxs-lookup"><span data-stu-id="6143e-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="6143e-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6143e-123">See also</span></span>

[<span data-ttu-id="6143e-124">在商務用 Skype Server 中規劃 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="6143e-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

