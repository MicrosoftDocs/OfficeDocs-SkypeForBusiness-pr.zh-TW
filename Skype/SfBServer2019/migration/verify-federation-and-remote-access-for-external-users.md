---
title: 驗證同盟及外部使用者的遠端存取
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
description: 將同盟路由轉換為商務用 Skype Server 2019 Edge Server 之後，您應該執行一些功能測試，以確認同盟如預期般執行。 外部使用者存取的測試應該包含組織支援的每種外部使用者類型，包括下列任一項或所有項目。
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751665"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="578c6-104">驗證同盟及外部使用者的遠端存取</span><span class="sxs-lookup"><span data-stu-id="578c6-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="578c6-105">將同盟路由轉換為商務用 Skype Server 2019 Edge Server 之後，您應該執行一些功能測試，以確認同盟如預期般執行。</span><span class="sxs-lookup"><span data-stu-id="578c6-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="578c6-106">外部使用者存取的測試應該包含組織支援的每種外部使用者類型，包括下列任一項或所有項目。</span><span class="sxs-lookup"><span data-stu-id="578c6-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="578c6-107">測試外部使用者與外部存取的連線能力</span><span class="sxs-lookup"><span data-stu-id="578c6-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="578c6-108">至少一個同盟網域的使用者、商務用 Skype Server 2019 的內部使用者，以及舊版安裝中的使用者。</span><span class="sxs-lookup"><span data-stu-id="578c6-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="578c6-109">測試立即訊息 (IM)、目前狀態、音訊/視訊 (A/V) 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="578c6-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="578c6-110">您的組織支援的每個公用 IM 服務提供者（及已布建）的使用者，與商務用 Skype Server 2019 上的使用者和舊版安裝上的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="578c6-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="578c6-111">確認匿名使用者可以加入會議。</span><span class="sxs-lookup"><span data-stu-id="578c6-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="578c6-112">在舊版安裝中使用遠端使用者存取的使用者（記錄如何從內部網路以外的 Lync Server/商務用 Skype 進行記錄，但沒有 VPN）和商務用 Skype Server 2019 上的使用者，以及舊版安裝中的使用者。</span><span class="sxs-lookup"><span data-stu-id="578c6-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="578c6-113">測試 IM、目前狀態、A/V 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="578c6-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="578c6-114">在商務用 Skype 2019 Server 上主控的使用者，使用遠端使用者存取（從內部網路以外的商務用 Skype Server 2019 登入，但不含 VPN）與商務用 Skype Server 2019 上的使用者，以及舊版安裝中的使用者。</span><span class="sxs-lookup"><span data-stu-id="578c6-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="578c6-115">測試 IM、目前狀態、A/V 及桌面共用。</span><span class="sxs-lookup"><span data-stu-id="578c6-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

