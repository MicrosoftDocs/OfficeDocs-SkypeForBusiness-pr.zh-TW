---
title: 中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 您可以在此對話方塊中編輯中繼伺服器的屬性。 沿左側是一組快速連結，可將您帶到 [一般設定]、[下個躍點設定] 和 [PSTN 閘道設定] 的設定。 在每個區段中都有下列設定：
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684546"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b6538-105">中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="b6538-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="b6538-106">您可以在此對話方塊中編輯中繼伺服器的屬性。</span><span class="sxs-lookup"><span data-stu-id="b6538-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="b6538-107">沿左側是一組快速連結，可將您帶到 [一般設定]、[下個躍點設定] 和 [PSTN 閘道設定] 的設定。</span><span class="sxs-lookup"><span data-stu-id="b6538-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="b6538-108">在每個區段中都有下列設定：</span><span class="sxs-lookup"><span data-stu-id="b6538-108">In each section are the following settings:</span></span>

 <span data-ttu-id="b6538-109">**一般**：</span><span class="sxs-lookup"><span data-stu-id="b6538-109">**General**:</span></span>

- <span data-ttu-id="b6538-110">**FQDN**：編輯中繼伺服器的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="b6538-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="b6538-111">**關聯**：選取 [**關聯邊緣池] （適用于 [媒體元件]）** 核取方塊，然後選取要用來做為外部存取媒體路徑的中繼伺服器的邊緣伺服器或邊緣池。</span><span class="sxs-lookup"><span data-stu-id="b6538-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="b6538-112">**下一個躍點**：</span><span class="sxs-lookup"><span data-stu-id="b6538-112">**Next hop**:</span></span>

- <span data-ttu-id="b6538-113">**下一個躍點選取**：從清單中選取 [前端伺服器] 或 [頂層端] 池，以做為用於與您的部署進行通訊的中繼伺服器路徑。</span><span class="sxs-lookup"><span data-stu-id="b6538-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="b6538-114">**PSTN 閘道**：</span><span class="sxs-lookup"><span data-stu-id="b6538-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="b6538-115">**中繼伺服器 PSTN 閘道**：</span><span class="sxs-lookup"><span data-stu-id="b6538-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="b6538-116">**偵聽埠**：定義轉送伺服器將偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="b6538-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="b6538-117">您可以為**TLS**或傳輸層安全性（或**TCP**）或傳輸控制通訊協定定義埠。</span><span class="sxs-lookup"><span data-stu-id="b6538-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="b6538-118">若要使用 TCP 的埠專案，您必須選取 [**啟用 TCP 埠**] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b6538-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b6538-119">請參閱您的公用交換電話網絡（PSTN）閘道的檔和設定設定，以判斷您是否需要啟用和定義埠值 TLS、TCP 或兩者。</span><span class="sxs-lookup"><span data-stu-id="b6538-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="b6538-120">TLS 是更安全的通訊協定，使用憑證來加密中繼伺服器與 PSTN 閘道之間的流量。</span><span class="sxs-lookup"><span data-stu-id="b6538-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="b6538-121">並非所有 PSTN 閘道都支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="b6538-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="b6538-122">系統會列出 SIP trunks 及針對您的部署定義及設定的閘道清單。</span><span class="sxs-lookup"><span data-stu-id="b6538-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="b6538-123">如果沒有任何專案出現，則表示您的部署沒有設定 SIP trunks 或 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="b6538-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="b6538-124">您可以在拓撲建立器中的 [**共用元件**] 底下定義及設定 trunks 和閘道。</span><span class="sxs-lookup"><span data-stu-id="b6538-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6538-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b6538-125">See also</span></span>

[<span data-ttu-id="b6538-126">SIP 中繼概覽</span><span class="sxs-lookup"><span data-stu-id="b6538-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="b6538-127">PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="b6538-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
