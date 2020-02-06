---
title: 設定試驗集區部署的 DNS 記錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在部署試驗池之前，您必須更新 DNS 主機 A 試驗池的專案。 若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: 94e5047dc82b0ddb55b03ad5c466011878c05ae7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813851"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="1d402-104">設定試驗集區部署的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="1d402-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="1d402-105">在部署試驗池之前，您必須更新 DNS 主機 A 試驗池的專案。</span><span class="sxs-lookup"><span data-stu-id="1d402-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="1d402-106">若要成功完成此程式，您應該以網域系統管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="1d402-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="1d402-107">設定 DNS 主機 A 記錄</span><span class="sxs-lookup"><span data-stu-id="1d402-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="1d402-108">在 [網域名稱系統（DNS）] 伺服器上，按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="1d402-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="1d402-109">在您網域的 [主控台樹] 中，展開 [**轉寄查閱區域**]，然後以滑鼠右鍵按一下將在其中安裝商務用 Skype Server 2019 的網域。</span><span class="sxs-lookup"><span data-stu-id="1d402-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="1d402-110">按一下 **[新增主機（A 或 AAAA）**]。</span><span class="sxs-lookup"><span data-stu-id="1d402-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="1d402-111">按一下 [**名稱**]，輸入商務用 Skype Server 2019 池的主機名稱（功能變數名稱是從定義該記錄的區域中假設，而且不需要輸入為 A 記錄的一部分）。</span><span class="sxs-lookup"><span data-stu-id="1d402-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="1d402-112">按一下 [ **IP 位址**]，然後輸入前端池的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1d402-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="1d402-113">按一下 [**新增主機**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1d402-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="1d402-114">完成後，請按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="1d402-114">When you are finished, click **Done**.</span></span>
    

