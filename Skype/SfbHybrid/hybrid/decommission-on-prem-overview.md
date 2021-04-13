---
title: 解除您的內部部署商務用 Skype 環境
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 如何解除委任您的內部部署商務用 Skype 環境的指示。
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656679"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="5ca5b-103">解除您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="5ca5b-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="5ca5b-104">如果您的組織使用團隊或商務用 Skype Online 搭配內部部署商務用 Skype Server，您可以將這些環境完全遷移至雲端，然後淘汰內部部署的商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ca5b-105">在解除委任內部部署環境之前，您必須 [設定](configure-hybrid-connectivity.md) 內部部署與 Microsoft 365 之間的混合式連線。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="5ca5b-106">設定混合式連線後，您可以將使用者遷移至雲端，同時從內部部署遷移其會議，以及從商務用 Skype 伺服器將任何連絡人遷移至小組。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="5ca5b-107">設定混合式連線是將使用者從內部部署遷移至雲端的必要步驟，以確保完整的團隊功能。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="5ca5b-108">若要完成從內部部署到雲端的移動，並解除委任您的內部部署商務用 Skype 伺服器環境，您必須依下列順序完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5ca5b-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="5ca5b-109">**步驟 1.**</span><span class="sxs-lookup"><span data-stu-id="5ca5b-109">**Step 1.**</span></span> <span data-ttu-id="5ca5b-110">[將所有必要使用者從內部部署移至線上](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-110">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="5ca5b-111">**步驟 2.**</span><span class="sxs-lookup"><span data-stu-id="5ca5b-111">**Step 2.**</span></span> <span data-ttu-id="5ca5b-112">[停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="5ca5b-113">**步驟 3.**</span><span class="sxs-lookup"><span data-stu-id="5ca5b-113">**Step 3.**</span></span> <span data-ttu-id="5ca5b-114">[將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-114">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="5ca5b-115">**步驟 4.**</span><span class="sxs-lookup"><span data-stu-id="5ca5b-115">**Step 4.**</span></span> <span data-ttu-id="5ca5b-116">[移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca5b-116">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

