---
title: 中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 您可以在此對話方塊中編輯轉送伺服器的屬性。 左側是可前往 [一般] 設定、[下一個躍點] 設定及 [ PSTN 閘道] 設定的一組快速連結。 每個區段包含下列設定：
ms.openlocfilehash: 6c8c238ce7d89db53f3b92a0f513c080976a3bab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114189"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="4276d-105">中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="4276d-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="4276d-106">您可以在此對話方塊中編輯轉送伺服器的屬性。</span><span class="sxs-lookup"><span data-stu-id="4276d-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="4276d-107">左側是可前往 [一般] 設定、[下一個躍點] 設定及 [ PSTN 閘道] 設定的一組快速連結。</span><span class="sxs-lookup"><span data-stu-id="4276d-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="4276d-108">每個區段包含下列設定：</span><span class="sxs-lookup"><span data-stu-id="4276d-108">In each section are the following settings:</span></span>

 <span data-ttu-id="4276d-109">**一般**：</span><span class="sxs-lookup"><span data-stu-id="4276d-109">**General**:</span></span>

- <span data-ttu-id="4276d-110">**FQDN**：編輯轉送伺服器的完整功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="4276d-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="4276d-111">**關聯**：選取 [ **關聯 edge 集區 (的媒體) 元件** ] 核取方塊，然後選取要用來做為外部存取之媒體路徑的轉送伺服器的 edge Server 或 edge 集區。</span><span class="sxs-lookup"><span data-stu-id="4276d-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="4276d-112">**下一個躍點**：</span><span class="sxs-lookup"><span data-stu-id="4276d-112">**Next hop**:</span></span>

- <span data-ttu-id="4276d-113">**下一個躍點選取**：從清單中選取前端伺服器或前端集區，以作為轉送伺服器的路徑，以用於與您的部署進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4276d-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="4276d-114">**PSTN 閘道**：</span><span class="sxs-lookup"><span data-stu-id="4276d-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="4276d-115">**中繼伺服器 PSTN 閘道**：</span><span class="sxs-lookup"><span data-stu-id="4276d-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="4276d-116">**聆聽埠**：定義轉送伺服器將接聽的埠。</span><span class="sxs-lookup"><span data-stu-id="4276d-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="4276d-117">您可以定義 TLS (傳輸層安全性) 或 TCP (傳輸控制通訊協定) 連接埠。</span><span class="sxs-lookup"><span data-stu-id="4276d-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="4276d-118">若要使用 TCP 連接埠項目，您必須選取 [啟用 TCP 連接埠] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4276d-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4276d-119">請參閱公用交換電話網路 (PSTN) 閘道的文件和組態設定，以決定是否需要啟用及定義連接埠值 TLS 及 (或) TCP。</span><span class="sxs-lookup"><span data-stu-id="4276d-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="4276d-120">TLS 是一種更安全的通訊協定，使用憑證來加密轉送伺服器和 PSTN 閘道之間的流量。</span><span class="sxs-lookup"><span data-stu-id="4276d-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="4276d-121">並非所有 PSTN 閘道都支援 TLS。</span><span class="sxs-lookup"><span data-stu-id="4276d-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="4276d-122">以下列出針對部署定義及設定的 SIP 主幹和閘道清單。</span><span class="sxs-lookup"><span data-stu-id="4276d-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="4276d-123">如果不存在任何項目，則部署未設定任何 SIP 主幹 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="4276d-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="4276d-124">您可以在拓撲產生器中定義及設定 [ **共用元件** ] 底下的主幹與閘道。</span><span class="sxs-lookup"><span data-stu-id="4276d-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="4276d-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4276d-125">See also</span></span>

[<span data-ttu-id="4276d-126">SIP 主幹連線概觀</span><span class="sxs-lookup"><span data-stu-id="4276d-126">Overview of SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[<span data-ttu-id="4276d-127">PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="4276d-127">PSTN Gateway Deployment Options</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)