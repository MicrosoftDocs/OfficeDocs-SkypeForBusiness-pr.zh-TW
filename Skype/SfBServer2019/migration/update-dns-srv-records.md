---
title: 更新 DNS SRV 記錄
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
description: 若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753265"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="9cb59-103">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="9cb59-103">Update DNS SRV records</span></span>

<span data-ttu-id="9cb59-104">若要順利完成此程式，您應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="9cb59-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="9cb59-105">本主題說明如何在遷移至商務用 Skype Server 2019 後，更新網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="9cb59-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="9cb59-106">在所有使用者移至商務用 Skype Server 2019，但在解除舊版集區或 Director 之前，您必須針對每個 SIP 網域更新內部 DNS 中的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="9cb59-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="9cb59-107">此程式假設您的內部 DNS 具有您 SIP 使用者網域的區域。</span><span class="sxs-lookup"><span data-stu-id="9cb59-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="9cb59-108">設定 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="9cb59-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="9cb59-109">在 DNS 伺服器上，按一下 [**開始**]，按一下 [系統**管理工具**]，然後按一下 [ **DNS**]。</span><span class="sxs-lookup"><span data-stu-id="9cb59-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="9cb59-110">在 SIP 網域的主控台樹中，展開 [**正向對應區域**]，展開安裝商務用 Skype Server 2019 的 SIP 網域，然後流覽至 [ **_tcp** ] 設定。</span><span class="sxs-lookup"><span data-stu-id="9cb59-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="9cb59-111">在右窗格中，以滑鼠右鍵按一下 [ **_sipinternaltls** ]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="9cb59-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="9cb59-112">在 [**提供這項服務的主機**] 中，將主機 FQDN 更新為指向商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="9cb59-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="9cb59-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9cb59-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="9cb59-114">確認可解析前端集區或 Standard Edition server 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9cb59-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="9cb59-115">登入網域中的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="9cb59-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="9cb59-116">按一下 [開始]\*\*\*\*，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9cb59-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="9cb59-117">在 [**開啟**] 方塊中輸入 cmd，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9cb59-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="9cb59-118">在命令提示字元中輸入 nslookup _\<FQDN of the Front End pool\>_ 或 _\<FQDN of the Standard Edition server\>_ ，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="9cb59-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="9cb59-119">請確認您收到的回復可解析為 FQDN 的適當 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9cb59-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

