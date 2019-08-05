---
title: 在商務用 Skype Server 中設定 trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在企業語音部署中, 您可以設定在中繼伺服器與一或多個對等之間的幹線, 為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡 (PSTN) 連線。
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187048"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="78280-103">在商務用 Skype Server 中設定 trunks</span><span class="sxs-lookup"><span data-stu-id="78280-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="78280-104">在企業語音部署中, 您可以設定在中繼伺服器與一或多個下列對等之間的幹線, 為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡 (PSTN) 連線:</span><span class="sxs-lookup"><span data-stu-id="78280-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="78280-105">網際網路電話服務提供者 (ITSP) 的 SIP 中繼連線</span><span class="sxs-lookup"><span data-stu-id="78280-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="78280-106">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="78280-106">PSTN gateway</span></span>
- <span data-ttu-id="78280-107">私人分支 exchange (PBX)</span><span class="sxs-lookup"><span data-stu-id="78280-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="78280-108">如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃 PSTN](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)連線。</span><span class="sxs-lookup"><span data-stu-id="78280-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78280-109">開始中繼設定前, 請確認已建立拓撲, 且已設定並與其他中繼伺服器及其對等專案相關聯。</span><span class="sxs-lookup"><span data-stu-id="78280-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="78280-110">如需詳細資訊, 請參閱[在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="78280-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78280-111">在主幹設定中, 您可以啟用商務用 Skype Server 媒體旁路功能, 這可讓媒體略過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="78280-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="78280-112">Trunks 可以使用或不啟用媒體旁路進行設定, 但我們強烈建議您啟用它。</span><span class="sxs-lookup"><span data-stu-id="78280-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="78280-113">如需詳細資訊, 請參閱[在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="78280-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
