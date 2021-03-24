---
title: 新增 Edge 電腦內部 IP
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: 使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。
ms.openlocfilehash: ff6c965c6256e26ebe905ce25e15c9e18a2cd0d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095817"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="a902f-103">新增 Edge 電腦內部 IP</span><span class="sxs-lookup"><span data-stu-id="a902f-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="a902f-104">使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a902f-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="a902f-105">您指定的 FQDN 必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="a902f-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a902f-106">根據預設，未加入網域的電腦的電腦名稱是簡短名稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a902f-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a902f-107">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="a902f-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a902f-108">因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定網域名稱系統 (DNS) 尾碼。</span><span class="sxs-lookup"><span data-stu-id="a902f-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a902f-109">如需在電腦名稱中加上 DNS 尾碼的詳細資訊，請參閱＜[Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)＞。</span><span class="sxs-lookup"><span data-stu-id="a902f-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>