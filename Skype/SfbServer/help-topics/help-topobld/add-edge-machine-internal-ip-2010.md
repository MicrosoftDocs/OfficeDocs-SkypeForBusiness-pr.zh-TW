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
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。
ms.openlocfilehash: 857e2041779efd02007939b7046860cc295cb7b8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219374"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="2c136-103">新增 Edge 電腦內部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="2c136-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="2c136-104">使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="2c136-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="2c136-105">在 [ **內部 IPv4 位址**] 中，輸入要新增至集區之 Edge SERVER 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2c136-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="2c136-106">在 [ **內部 FQDN**] 中，輸入您要新增至集區之 Edge Server 的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="2c136-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="2c136-107">您指定的 FQDN 必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="2c136-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="2c136-108">根據預設，未加入網域的電腦的電腦名稱是簡短名稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2c136-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2c136-109">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="2c136-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2c136-110">因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定網域名稱系統 (DNS) 尾碼。</span><span class="sxs-lookup"><span data-stu-id="2c136-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="2c136-111">如需在電腦名稱中加上 DNS 尾碼的詳細資訊，請參閱＜[Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="2c136-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


