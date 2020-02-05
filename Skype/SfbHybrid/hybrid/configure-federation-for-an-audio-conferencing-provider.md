---
title: 設定混合式部署中的音訊會議提供者的同盟
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
description: 摘要： 了解如何在 Skype for Business Online 設定音訊會議提供者同盟。
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726883"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="d18c2-103">設定混合式部署中的音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="d18c2-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="d18c2-104">**摘要：** 了解如何在 Skype for Business Online 設定音訊會議提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="d18c2-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="d18c2-105">如果您想要在混合式部署 （內部部署與線上） 中使用音訊會議提供者 (ACP)，您需要將您的內部部署和 ACP 夥伴之間的同盟設定為允許協力程式伺服器。</span><span class="sxs-lookup"><span data-stu-id="d18c2-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="d18c2-106">您可以設定同盟新增 Edge server （這也稱為 Access Proxy） 與 ACP 協力廠商網域到同盟網域清單為您的內部部署。</span><span class="sxs-lookup"><span data-stu-id="d18c2-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="d18c2-107">ACP 夥伴然後必須允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d18c2-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="d18c2-108">如需詳細資訊，請連絡您 ACP 提供者。</span><span class="sxs-lookup"><span data-stu-id="d18c2-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="d18c2-109">ACP 夥伴然後必須允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d18c2-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="d18c2-110">**新增 Edge Server 與 ACP 網域為允許同盟網域**</span><span class="sxs-lookup"><span data-stu-id="d18c2-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="d18c2-111">若要新增 ACP 網域為允許協力程式伺服器 （允許同盟網域），請遵循[設定支援允許的外部網域](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="d18c2-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="d18c2-112">針對 Edge Server] 新增 ACP 夥伴的 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d18c2-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="d18c2-113">您可能需要您取得其 Edge Server，可能也會參照您 ACP 作為其 Access Proxy FQDN 的 ACP 合作夥伴連絡。</span><span class="sxs-lookup"><span data-stu-id="d18c2-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="d18c2-114">**ACP 協力廠商提供 Edge Server 集區的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="d18c2-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="d18c2-115">ACP 合作夥伴必須設定為允許協力程式伺服器新增您的內部部署網域新增 Edge Server 集區的 FQDN，以允許同盟網域同盟。</span><span class="sxs-lookup"><span data-stu-id="d18c2-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


