---
title: 新增 Edge Server 內部 IP 2010
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: 使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。
ms.openlocfilehash: 2f60eef6392b335461a9e0fc427c19d9f1d7b661
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219194"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="fca26-103">新增 Edge Server 內部 IP 2010</span><span class="sxs-lookup"><span data-stu-id="fca26-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="fca26-104">使用此頁面指定 Edge Server 的內部 IP 位址和內部完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="fca26-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="fca26-105">您指定的 FQDN 必須與伺服器上設定的電腦名稱相同。</span><span class="sxs-lookup"><span data-stu-id="fca26-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="fca26-106">根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fca26-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="fca26-107">拓撲產生器使用 Fqdn，而非短名稱。</span><span class="sxs-lookup"><span data-stu-id="fca26-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="fca26-108">因此，在要部署為 Edge Server 的電腦 (未加入網域) 名稱中，您必須設定網域名稱系統 (DNS) 尾碼。</span><span class="sxs-lookup"><span data-stu-id="fca26-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="fca26-109">如需將 DNS 尾碼新增至電腦名稱稱的詳細資訊，請參閱 [CONFIGURE dns For Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fca26-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).</span></span>


