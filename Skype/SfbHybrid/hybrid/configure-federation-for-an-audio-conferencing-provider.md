---
title: 為混合式部署中的音訊會議提供者設定同盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.custom: ''
description: 摘要：瞭解如何為商務用 Skype Online 中的音訊會議提供者設定同盟。
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118972"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="3d64a-103">為混合式部署中的音訊會議提供者設定同盟</span><span class="sxs-lookup"><span data-stu-id="3d64a-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="3d64a-104">**摘要：** 瞭解如何為商務用 Skype Online 中的音訊會議提供者設定同盟。</span><span class="sxs-lookup"><span data-stu-id="3d64a-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="3d64a-105">如果您想要在混合部署中使用音訊會議提供者 (ACP)  (內部部署與線上) ，您必須設定內部部署與 ACP 夥伴之間的同盟為允許的夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="3d64a-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="3d64a-106">您可以新增 ACP partner domain 及 Edge server (此設定同盟也稱為存取 Proxy) 內部部署的同盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="3d64a-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="3d64a-107">您的 ACP 合作夥伴必須將您的內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="3d64a-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="3d64a-108">如需其他詳細資料，請與您的 ACP 提供者聯繫。</span><span class="sxs-lookup"><span data-stu-id="3d64a-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="3d64a-109">您的 ACP 合作夥伴必須將您的內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。</span><span class="sxs-lookup"><span data-stu-id="3d64a-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="3d64a-110">**將 ACP 網域和 Edge Server 新增為允許的同盟網域**</span><span class="sxs-lookup"><span data-stu-id="3d64a-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="3d64a-111">若要將 ACP 網域新增為允許的同盟伺服器 (允許的同盟網域) ，請依照 [Configure Support for The 允許的外部網域](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="3d64a-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="3d64a-112">針對 Edge Server，新增 ACP partner Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d64a-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="3d64a-113">您可能需要聯繫 ACP 合作夥伴，以取得其 Edge Server 的 FQDN，而您的 ACP 也可能會將其稱為存取 Proxy。</span><span class="sxs-lookup"><span data-stu-id="3d64a-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="3d64a-114">**提供 Edge Server 集區的 FQDN 至 ACP partner**</span><span class="sxs-lookup"><span data-stu-id="3d64a-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="3d64a-115">ACP 合作夥伴必須將 Edge Server 集區的 FQDN 新增為允許的同盟網域，才能設定同盟以將您的內部部署網域新增為允許的夥伴伺服器。</span><span class="sxs-lookup"><span data-stu-id="3d64a-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>