---
title: 同盟路由設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 若要設定網站同盟路由指派，您必須先在 Edge Server 或 Edge Server 集區上啟用同盟。如果 Edge Server 或集區上未啟用同盟，則無法修改網站的同盟路由指派設定。
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819463"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="ddd64-104">同盟路由設定展開工具</span><span class="sxs-lookup"><span data-stu-id="ddd64-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="ddd64-p102">若要設定網站同盟路由指派，您必須先在 Edge Server 或 Edge Server 集區上啟用同盟。如果 Edge Server 或集區上未啟用同盟，則無法修改網站的同盟路由指派設定。</span><span class="sxs-lookup"><span data-stu-id="ddd64-p102">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool. If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="ddd64-107">如果已設定 Edge Server 或集區上的同盟設定，則可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="ddd64-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="ddd64-108">**允許對所有網站的同盟路由指派** 此設定會影響所有網站。</span><span class="sxs-lookup"><span data-stu-id="ddd64-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="ddd64-109">請確定您在此網站上設定的設定適用于所有網站。</span><span class="sxs-lookup"><span data-stu-id="ddd64-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="ddd64-110">**啟用 SIP 同盟** 選取此選項可啟用 SIP 同盟路由，然後選取 Director 或 Edge 集區作為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="ddd64-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="ddd64-111">**啟用 XMPP 同盟** 選取此選項可啟用 XMPP 同盟路由，然後選取 Director 或 Edge 集區作為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="ddd64-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="ddd64-112">XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。</span><span class="sxs-lookup"><span data-stu-id="ddd64-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ddd64-113">如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。</span><span class="sxs-lookup"><span data-stu-id="ddd64-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

