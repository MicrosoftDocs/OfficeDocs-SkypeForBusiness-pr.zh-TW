---
title: 驗證外部使用者的同盟與遠端存取權
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 將同盟路由轉換為商務用 Skype Server 2019 Edge 伺服器之後, 您應該執行一些功能測試, 以驗證同盟是否如預期方式執行。 外部使用者存取的測試應該包括貴組織支援的每一種外部使用者類型, 包括下列任一或所有類型的使用者。
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192342"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="b7577-104">驗證外部使用者的同盟與遠端存取權</span><span class="sxs-lookup"><span data-stu-id="b7577-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="b7577-105">將同盟路由轉換為商務用 Skype Server 2019 Edge 伺服器之後, 您應該執行一些功能測試, 以驗證同盟是否如預期方式執行。</span><span class="sxs-lookup"><span data-stu-id="b7577-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="b7577-106">外部使用者存取的測試應該包括貴組織支援的每一種外部使用者類型, 包括下列任一或所有類型的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7577-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="b7577-107">測試外部使用者與外部存取的連通性</span><span class="sxs-lookup"><span data-stu-id="b7577-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="b7577-108">至少一個聯盟網域中的使用者、商務用 Skype Server 2019 上的內部使用者, 以及舊版安裝的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7577-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="b7577-109">測試立即訊息 (IM)、目前狀態、音訊/視頻 (A/V) 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="b7577-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="b7577-110">貴組織支援的每個公用 IM 服務提供者的使用者 (以及已完成哪些預配) 與商務用 Skype Server 2019 上的使用者通訊, 以及舊版安裝的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7577-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="b7577-111">確認匿名使用者可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="b7577-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="b7577-112">在舊版安裝中使用遠端使用者存取 (記錄我不含 VPN 的 Lync Server/商務用 Skype) 與商務用 Skype Server 2019 上的使用者, 以及舊版安裝使用者的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7577-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="b7577-113">測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="b7577-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="b7577-114">在商務用 Skype Server 2019 上使用 [遠端使用者存取] (從內部網路外部 2019 (不含 VPN), 使用商務用 Skype Server 2019 上的使用者, 以及舊版安裝的使用者, 在商務用 Skype Server 上託管的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7577-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="b7577-115">測試 IM、目前狀態、A/V 與桌面共用。</span><span class="sxs-lookup"><span data-stu-id="b7577-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

