---
title: 在混合式部署中設定音訊會議提供者的同盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '摘要: 瞭解如何在商務用 Skype Online 中設定音訊會議提供者的同盟。'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185461"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="271ae-103">在混合式部署中設定音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="271ae-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="271ae-104">**摘要:** 瞭解如何在商務用 Skype Online 中設定音訊會議提供者的同盟。</span><span class="sxs-lookup"><span data-stu-id="271ae-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="271ae-105">如果您想要在混合式部署中使用音訊會議提供者 (ACP), 您需要在內部部署和 ACP 夥伴之間設定同盟作為允許的合作夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="271ae-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="271ae-106">您可以將 ACP 夥伴網域和 Edge 伺服器 (也稱為 [存取代理伺服器]) 新增到內部部署的 [聯盟網域] 清單中, 以設定同盟。</span><span class="sxs-lookup"><span data-stu-id="271ae-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="271ae-107">您的 ACP 合作夥伴接著需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="271ae-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="271ae-108">如需其他詳細資料, 請與您的 ACP 提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="271ae-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="271ae-109">您的 ACP 合作夥伴接著需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="271ae-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="271ae-110">**新增 ACP 網域和 Edge 伺服器作為允許的聯盟網域**</span><span class="sxs-lookup"><span data-stu-id="271ae-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="271ae-111">若要將 ACP 網域新增為允許的夥伴伺服器 (允許聯盟網域), 請依照[設定支援的外部網域](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)中的步驟操作。</span><span class="sxs-lookup"><span data-stu-id="271ae-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="271ae-112">針對 Edge 伺服器, 新增 ACP 合作夥伴邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="271ae-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="271ae-113">您可能需要與您的 ACP 夥伴聯繫, 以取得其 Edge 伺服器的 FQDN, 您的 ACP 也可能會將其稱為存取 Proxy。</span><span class="sxs-lookup"><span data-stu-id="271ae-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="271ae-114">**將 Edge 伺服器池的 FQDN 提供給 ACP 合作夥伴**</span><span class="sxs-lookup"><span data-stu-id="271ae-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="271ae-115">ACP 合作夥伴需要設定同盟, 只要將 Edge 伺服器池的 FQDN 新增為允許的聯盟網域, 即可將您的內部部署網域新增為允許的合作夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="271ae-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


