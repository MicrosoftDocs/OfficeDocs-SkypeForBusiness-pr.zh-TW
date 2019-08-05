---
title: 在商務用 Skype Server 中部署企業版語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: '摘要: 瞭解如何在中央網站部署商務用 Skype Server 的企業語音。'
ms.openlocfilehash: c5995570d8d3cf775b2837bb6ddfc170860d57dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191950"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="4e8cb-103">在商務用 Skype Server 中部署企業版語音</span><span class="sxs-lookup"><span data-stu-id="4e8cb-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="4e8cb-104">**摘要:** 瞭解如何在中央網站部署商務用 Skype Server 的企業語音。</span><span class="sxs-lookup"><span data-stu-id="4e8cb-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="4e8cb-105">您可以在中央網站使用本主題來部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="4e8cb-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="4e8cb-106">若要在分支網站上部署企業語音, 請跳過[部署分支網站](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4e8cb-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="4e8cb-107">本節包含適用于部署的程式, 其中, 在每個前端伺服器或標準版伺服器上 collocated 的中繼伺服器 (如有建議), 以及使用獨立的中繼伺服器池的部署。如果您使用拓撲建立器定義併發布在每個前端伺服器或標準版伺服器上 collocates 轉送伺服器的拓撲, 就可以略過下列內容, 因為部署嚮導已自動安裝檔案供當您為前端伺服器池或標準版伺服器安裝檔案時, 會進行中繼伺服器:</span><span class="sxs-lookup"><span data-stu-id="4e8cb-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="4e8cb-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="4e8cb-108">In this section</span></span>

- [<span data-ttu-id="4e8cb-109">商務用 Skype Server 中的企業語音安全性與設定先決條件</span><span class="sxs-lookup"><span data-stu-id="4e8cb-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- <span data-ttu-id="4e8cb-110">[在商務用 Skype Server 的 [拓撲產生器] 中部署轉送伺服器](deploy-a-mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="4e8cb-110">[Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md)</span></span>

- <span data-ttu-id="4e8cb-111">[在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道](define-a-gateway.md)</span><span class="sxs-lookup"><span data-stu-id="4e8cb-111">[Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md)</span></span>

- <span data-ttu-id="4e8cb-112">[在商務用 Skype Server 的 [拓撲產生器] 中定義其他 trunks](define-additional-trunks.md)</span><span class="sxs-lookup"><span data-stu-id="4e8cb-112">[Define additional trunks in Topology Builder in Skype for Business Server](define-additional-trunks.md)</span></span>

- [<span data-ttu-id="4e8cb-113">在商務用 Skype Server 中安裝用於轉送服務伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="4e8cb-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="4e8cb-114">在商務用 Skype Server 中設定 trunks</span><span class="sxs-lookup"><span data-stu-id="4e8cb-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="4e8cb-115">在商務用 Skype Server 中建立或修改呼叫者識別碼簡報的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="4e8cb-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="4e8cb-116">在商務用 Skype Server 中建立或修改呼叫 ID 簡報的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="4e8cb-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="4e8cb-117">在商務用 Skype 中建立或修改正常化規則</span><span class="sxs-lookup"><span data-stu-id="4e8cb-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="4e8cb-118">在商務用 Skype Server 中建立或修改撥號方案</span><span class="sxs-lookup"><span data-stu-id="4e8cb-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="4e8cb-119">在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由</span><span class="sxs-lookup"><span data-stu-id="4e8cb-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="4e8cb-120">在商務用 Skype Server 中啟用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="4e8cb-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="4e8cb-121">在商務用 Skype Server 中部署高級企業語音功能</span><span class="sxs-lookup"><span data-stu-id="4e8cb-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="4e8cb-122">在商務用 Skype 中部署通話管理功能</span><span class="sxs-lookup"><span data-stu-id="4e8cb-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="4e8cb-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4e8cb-123">See also</span></span>

[<span data-ttu-id="4e8cb-124">商務用 Skype Server 中的企業語音方案</span><span class="sxs-lookup"><span data-stu-id="4e8cb-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

