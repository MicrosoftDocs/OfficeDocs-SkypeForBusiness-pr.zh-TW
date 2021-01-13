---
title: 新增 Edge Server 選項 (適用於 Lync Server 2010)
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 您會定義新的 Edge Server 或 Edge 集區，並會呈現機會，以定義新伺服器或集區的功能。 您可以選擇的選項包括：
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835513"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="fd061-104">新增 Edge Server 選項 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="fd061-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="fd061-105">您會定義新的 Edge Server 或 Edge 集區，並會呈現機會，以定義新伺服器或集區的功能。</span><span class="sxs-lookup"><span data-stu-id="fd061-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="fd061-106">您可以選擇的選項包括：</span><span class="sxs-lookup"><span data-stu-id="fd061-106">The options that you can choose are:</span></span>

- <span data-ttu-id="fd061-107">**使用單一 FQDN 和 IP 位址**：選取此核取方塊可針對外部 Edge 介面，使用單一 IPv4 或 IPv6 (如果選擇同時使用 IPv4 和 IPv6，則必須定義其中一種 IP 位址類型) 位址及完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fd061-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fd061-108">如果選擇這個選項，只會使用一個 IP 位址，或 IPv4 和 IPv6 各一個，但是必須為每個 Edge 介面指派不同的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fd061-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="fd061-109">**啟用同盟 (連接埠 5061)**：如果您想與使用工作階段初始通訊協定 (SIP) 的其他 SIP 同盟、提供者或託管服務進行同盟，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fd061-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="fd061-110">**此 Edge 集區的外部 IP 位址由 NAT 轉譯**：如果您對 Edge 外部介面使用私人 ip 位址，並提供網路位址轉譯 (NAT) 裝置，以在邏輯上放置 edge Server 或 edge 集區，則選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fd061-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd061-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd061-111">See also</span></span>

[<span data-ttu-id="fd061-112">規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="fd061-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="fd061-113">部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="fd061-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
