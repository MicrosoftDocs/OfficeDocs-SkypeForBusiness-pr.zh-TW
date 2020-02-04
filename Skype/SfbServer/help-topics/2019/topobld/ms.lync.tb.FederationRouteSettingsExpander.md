---
title: 同盟路由設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 若要設定網站同盟路由指派，您必須先在 Edge 伺服器或 Edge 伺服器池中啟用同盟。 如果在 Edge 伺服器或池中沒有啟用同盟，該網站的同盟路由指派設定將不會提供修改。
ms.openlocfilehash: a9679d5ddfe4652a79f58596940af7f450e4b470
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688559"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="0e55b-104">同盟路由設定展開工具</span><span class="sxs-lookup"><span data-stu-id="0e55b-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="0e55b-105">若要設定網站同盟路由指派，您必須先在 Edge 伺服器或 Edge 伺服器池中啟用同盟。</span><span class="sxs-lookup"><span data-stu-id="0e55b-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="0e55b-106">如果在 Edge 伺服器或池中沒有啟用同盟，該網站的同盟路由指派設定將不會提供修改。</span><span class="sxs-lookup"><span data-stu-id="0e55b-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="0e55b-107">如果已設定 Edge 伺服器或池中的同盟設定，您可以設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="0e55b-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="0e55b-108">**允許將同盟路由指派給所有網站**此設定會影響所有網站。</span><span class="sxs-lookup"><span data-stu-id="0e55b-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="0e55b-109">請確定您在此網站所設定的設定適用于所有網站。</span><span class="sxs-lookup"><span data-stu-id="0e55b-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="0e55b-110">**啟用 SIP 同盟**選取此選項以啟用 SIP 同盟路由，然後選取 Director 或 Edge 池做為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="0e55b-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="0e55b-111">**啟用 XMPP 同盟**選取此選項以啟用 XMPP 同盟路由，然後選取 Director 或 Edge 池做為同盟路由。</span><span class="sxs-lookup"><span data-stu-id="0e55b-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="0e55b-112">XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="0e55b-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0e55b-113">如需詳細資訊，請參閱[遷移 XMPP 同盟](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="0e55b-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

