---
title: 遷移 XMPP 同盟
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '先前的版本提供了可擴展的訊息和目前狀態通訊協定 (XMPP) 閘道, 可將其部署為個別的伺服器角色, 以允許與 XMPP 部署進行聯盟。 在商務用 Skype Server 2019 中, & 不贊成使用 XMPP 功能。 如果您想要繼續使用 XMPP 功能, 可以使用舊版版本 (商務用 Skype Server 2015/Lync Server 2013) availed 在 coexitence 環境中。 XMPP 功能安裝在兩個部分中: 作為在舊版 Edge 伺服器上執行的 XMPP proxy, 以及在舊版前端伺服器上執行的 XMPP 閘道。'
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238136"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="ec9fa-106">遷移 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="ec9fa-106">Migrating XMPP federation</span></span>

<span data-ttu-id="ec9fa-107">先前的版本提供了可擴展的訊息和目前狀態通訊協定 (XMPP) 閘道, 可將其部署為個別的伺服器角色, 以允許與 XMPP 部署進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-107">Previous versions provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="ec9fa-108">XMPP 功能已不再提供, 且在商務用 Skype Server 2019 中已過時。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-108">The XMPP functionality is no longer available and is deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="ec9fa-109">如果您想要繼續使用 XMPP 功能, 您可以在具有舊版環境 (商務用 Skype Server 2015 或 Lync Server 2013) 的共存環境中執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-109">If you want to continue with the XMPP functionality, you can do so in a coexistence environment with a legacy version (Skype for Business Server 2015 or Lync Server 2013).</span></span> <span data-ttu-id="ec9fa-110">XMPP 功能安裝在兩個部分中: 作為在舊版 Edge 伺服器上執行的 XMPP proxy, 以及在舊版前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-110">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the legacy Edge Server, and the XMPP Gateway that runs on the legacy Front End Server.</span></span> 
  
<span data-ttu-id="ec9fa-111">從遷移的角度而言, 想要使用 XMPP 功能的使用者應該保留在舊版伺服器中, 而且不應該移至 [商務用 Skype Server 2019], 但仍需繼續使用舊版 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-111">From a migration perspective, users who want to avail the XMPP feature should remain in the legacy server and should not be moved to a Skype for Business Server 2019 pool but continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="ec9fa-112">只有在商務用 Skype Server 2015 或 Lync Server 2013 中設定 XMPP 聯盟夥伴時, 才能這麼做。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-112">This is possible only when the XMPP federated partner is configured in Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="ec9fa-113">如果您想要繼續使用 XMPP 功能, 則不要將舊版 Edge 伺服器遷移到商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-113">You should not migrate the legacy Edge Server to Skype for Business Server 2019 if you want to continue with XMPP functionality.</span></span> <span data-ttu-id="ec9fa-114">不過, 您可以將舊版 Edge 伺服器 (與 XMPP Proxy) 與商務用 Skype 2019 Edge 伺服器共存。</span><span class="sxs-lookup"><span data-stu-id="ec9fa-114">However, you can have coexistence of the legacy Edge Server (with XMPP Proxy) and the Skype for Business 2019 Edge Server.</span></span>
  

    

