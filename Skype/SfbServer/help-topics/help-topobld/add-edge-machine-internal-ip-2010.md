---
title: 新增 Edge 電腦內部 IP 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此頁面來指定內部 IP 位址，以及邊緣伺服器的內部完整功能變數名稱（FQDN）。
ms.openlocfilehash: 4c1606dfc44a303b5e9eb8e84710b14b41b7da90
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685296"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="a1bc4-103">新增 Edge 電腦內部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="a1bc4-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="a1bc4-104">使用此頁面來指定內部 IP 位址，以及邊緣伺服器的內部完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="a1bc4-105">在 [**內部 IPv4 位址**] 中，輸入您要新增至池中的邊緣伺服器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="a1bc4-106">在**內部 FQDN**中，輸入您要新增至池中的邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="a1bc4-107">您指定的 FQDN 必須與伺服器上設定的電腦名稱稱相同。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="a1bc4-108">根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a1bc4-109">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a1bc4-110">因此，您必須在要部署成邊緣伺服器且未加入網域的電腦名稱稱上設定網域名稱系統（DNS）尾碼。</span><span class="sxs-lookup"><span data-stu-id="a1bc4-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a1bc4-111">如需新增 DNS 尾碼至電腦名稱稱的詳細資料，請參閱[設定 dns 以取得 Edge 支援](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="a1bc4-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


