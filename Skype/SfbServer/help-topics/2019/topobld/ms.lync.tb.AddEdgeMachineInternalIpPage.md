---
title: 新增 Edge 電腦內部 IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: 使用此頁面來指定邊緣伺服器的內部 IP 位址與內部完整功能變數名稱（FQDN）。
ms.openlocfilehash: a86293ac5bf659b47fe4b91591c70d80a1f41c34
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703098"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="5b042-103">新增 Edge 電腦內部 IP</span><span class="sxs-lookup"><span data-stu-id="5b042-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="5b042-104">使用此頁面來指定邊緣伺服器的內部 IP 位址與內部完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="5b042-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="5b042-105">您指定的 FQDN 必須與伺服器上設定的電腦名稱稱相同。</span><span class="sxs-lookup"><span data-stu-id="5b042-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="5b042-106">根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5b042-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="5b042-107">拓撲產生器會使用 FQDN，而非簡稱。</span><span class="sxs-lookup"><span data-stu-id="5b042-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="5b042-108">因此，您必須在要部署成邊緣伺服器且未加入網域的電腦名稱稱上設定網域名稱系統（DNS）尾碼。</span><span class="sxs-lookup"><span data-stu-id="5b042-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="5b042-109">如需新增 DNS 尾碼至電腦名稱稱的詳細資料，請參閱[設定 dns 以取得 Edge 支援](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="5b042-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


