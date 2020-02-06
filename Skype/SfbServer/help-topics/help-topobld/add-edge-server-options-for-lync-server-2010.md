---
title: 新增 Lync Server 2010 的 Edge Server 選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 您可以定義新的邊緣伺服器或 Edge 池，並供應商機來定義新伺服器或池中的功能。 您可以選擇的選項包括：
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820985"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="c3f78-104">新增 Lync Server 2010 的 Edge Server 選項</span><span class="sxs-lookup"><span data-stu-id="c3f78-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="c3f78-105">您可以定義新的邊緣伺服器或 Edge 池，並供應商機來定義新伺服器或池中的功能。</span><span class="sxs-lookup"><span data-stu-id="c3f78-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="c3f78-106">您可以選擇的選項包括：</span><span class="sxs-lookup"><span data-stu-id="c3f78-106">The options that you can choose are:</span></span>

- <span data-ttu-id="c3f78-107">**使用單一 FQDN 和 IP 位址**：選取核取方塊以使用單一 Ipv4 或 ipv6 （如果您選擇同時使用 Ipv4 和 ipv6），則必須為外部邊緣介面定義其中一個 IP 位址類型的位址和完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="c3f78-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c3f78-108">如果您選擇此選項，您將只使用一個 IP 位址或一個 IPv4 與一個 IPv6，但是您必須為每個 Edge 介面指派不同的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="c3f78-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="c3f78-109">**啟用同盟（埠5061）**：如果您要與其他 SIP 聯合體、提供者或使用會話初始通訊協定（SIP）的託管產品進行聯盟，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c3f78-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="c3f78-110">**此 edge 池的外部 ip 位址是由 NAT 來轉譯**：如果您針對 edge 外部介面使用私人 IP 位址，並提供網路位址轉譯（NAT）裝置，以邏輯方式放置邊緣伺服器或邊緣池，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c3f78-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3f78-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3f78-111">See also</span></span>

[<span data-ttu-id="c3f78-112">規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="c3f78-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="c3f78-113">部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="c3f78-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
