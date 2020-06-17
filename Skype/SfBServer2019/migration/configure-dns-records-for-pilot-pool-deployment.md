---
title: 為試驗集區部署設定 DNS 記錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署試驗集區之前，您必須更新 DNS 主機試驗集區的專案。 若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754053"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="4d728-104">為試驗集區部署設定 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4d728-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="4d728-105">部署試驗集區之前，您必須更新 DNS 主機的試驗集區的專案。</span><span class="sxs-lookup"><span data-stu-id="4d728-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="4d728-106">若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="4d728-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="4d728-107">設定 DNS 主機 A 記錄</span><span class="sxs-lookup"><span data-stu-id="4d728-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="4d728-108">在網域名稱系統 (DNS) 伺服器上，依序按一下 **[開始]**、**[系統管理工具]** 和 **[DNS]**。</span><span class="sxs-lookup"><span data-stu-id="4d728-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="4d728-109">在您網域的主控台樹中，展開 [**正向對應區域**]，然後在要安裝商務用 Skype Server 2019 的網域上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="4d728-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="4d728-110">按一下 **[新增主機 (A 或 AAAA)]**。</span><span class="sxs-lookup"><span data-stu-id="4d728-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="4d728-111">按一下 [**名稱**]，輸入商務用 Skype Server 2019 集區的主機名稱（功能變數名稱會從記錄定義所在的區域來假設，而不需輸入為 A 記錄的一部分）。</span><span class="sxs-lookup"><span data-stu-id="4d728-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="4d728-112">按一下 [ **IP 位址**]，然後輸入前端集區的 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="4d728-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="4d728-113">按一下 **[新增主機]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4d728-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="4d728-114">完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4d728-114">When you are finished, click **Done**.</span></span>
    

