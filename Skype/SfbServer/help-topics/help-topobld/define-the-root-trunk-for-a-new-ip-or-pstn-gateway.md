---
title: 定義新的 IP 或 PSTN 閘道的根主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: 您可以透過設定下列項目，來定義 IP 或公用交換電話網路 (PSTN) 的根主幹：
ms.openlocfilehash: bcb63361291d241139fb9eb126b26cd038ea8b34
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119672"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="37128-103">定義新的 IP 或 PSTN 閘道的根主幹</span><span class="sxs-lookup"><span data-stu-id="37128-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="37128-104">您可以透過設定下列項目，來定義 IP 或公用交換電話網路 (PSTN) 的根主幹：</span><span class="sxs-lookup"><span data-stu-id="37128-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="37128-105">**主幹名稱**：定義與主幹相關聯的完整網域名稱</span><span class="sxs-lookup"><span data-stu-id="37128-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="37128-106">**IP/PSTN 閘道的聆聽連接埠**：定義此主幹聆聽的連接埠</span><span class="sxs-lookup"><span data-stu-id="37128-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="37128-107">**SIP 傳輸通訊協定**：根據主幹需求，從清單中選取 [TCP] 或 [TLS]</span><span class="sxs-lookup"><span data-stu-id="37128-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="37128-108">**關聯** 的轉送伺服器：從部署中可用的轉送伺服器清單中選取</span><span class="sxs-lookup"><span data-stu-id="37128-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="37128-109">**關聯的轉送伺服器埠**：定義所選轉送伺服器正在接聽的埠</span><span class="sxs-lookup"><span data-stu-id="37128-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="37128-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="37128-110">See also</span></span>

[<span data-ttu-id="37128-111">在商務用 Skype Server 2015 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="37128-111">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="37128-112">在商務用 Skype Server 2015 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="37128-112">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="37128-113">SIP 主幹支援</span><span class="sxs-lookup"><span data-stu-id="37128-113">SIP Trunking Support</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunking-support)