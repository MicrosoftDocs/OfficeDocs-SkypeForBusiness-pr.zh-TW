---
title: Edge 設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 若要編輯現有單一或多部伺服器 Edge 集區的設定，您會看到下列各節：
ms.openlocfilehash: 5b4bbb302f76a38a5a485d17ad6df5c0d1db1c6b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119652"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="6051a-103">Edge 設定展開工具</span><span class="sxs-lookup"><span data-stu-id="6051a-103">Edge Settings Expander</span></span>

<span data-ttu-id="6051a-104">若要編輯現有單一或多部伺服器 Edge 集區的設定，您會看到下列各節：</span><span class="sxs-lookup"><span data-stu-id="6051a-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="6051a-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="6051a-105">General settings</span></span>

- <span data-ttu-id="6051a-106">下一個躍點選取設定</span><span class="sxs-lookup"><span data-stu-id="6051a-106">Next hop selection settings</span></span>

- <span data-ttu-id="6051a-107">Edge Server 設定</span><span class="sxs-lookup"><span data-stu-id="6051a-107">Edge Server configuration</span></span>



## <a name="general-settings"></a><span data-ttu-id="6051a-108">一般設定</span><span class="sxs-lookup"><span data-stu-id="6051a-108">General settings</span></span>

<span data-ttu-id="6051a-109">Edge Server 集區的內部集區完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="6051a-109">Internal pool fully qualified domain name (FQDN) of the Edge Server pool.</span></span> <span data-ttu-id="6051a-110">編輯集區的 FQDN，以變更此設定。</span><span class="sxs-lookup"><span data-stu-id="6051a-110">Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="6051a-111">選取 [啟用此 Edge 集區的同盟] 核取方塊。如果您要設定與 Lync Server 2013、Microsoft Lync Server 2010 或 Microsoft Office 通訊伺服器 2007 R2 信任的同盟搭配使用，請 **(埠 5061)** 。</span><span class="sxs-lookup"><span data-stu-id="6051a-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Lync Server 2013, Microsoft Lync Server 2010 or Microsoft Office Communications Server 2007 R2 trusted partner.</span></span>

<span data-ttu-id="6051a-112">選取 [ **啟用此 Edge 集區的 XMPP 同盟** ] 以啟用 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="6051a-112">Select **Enable XMPP federation for this Edge pool** to enable XMPP federation.</span></span>

<span data-ttu-id="6051a-113">指定內部配置複寫埠的埠號碼 **(HTTPS)**。</span><span class="sxs-lookup"><span data-stu-id="6051a-113">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="6051a-114">下一個躍點選取設定</span><span class="sxs-lookup"><span data-stu-id="6051a-114">Next hop selection settings</span></span>

<span data-ttu-id="6051a-115">若要設定或修改 Edge server 將用來與內部基礎結構通訊的 **下一個躍點** 集區，請從下拉式清單方塊中選取 Director、director 集區、前端伺服器或前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="6051a-115">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="6051a-116">只會顯示已在拓撲產生器中設定的 Director 或前端，以供選取。</span><span class="sxs-lookup"><span data-stu-id="6051a-116">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="6051a-117">Edge Server 設定</span><span class="sxs-lookup"><span data-stu-id="6051a-117">Edge Server configuration</span></span>

<span data-ttu-id="6051a-118">若要編輯或指定 Edge Server 的 **外部設定** 設定，您必須先決定是否要針對 SIP 存取、web 會議和 Audio/Video 服務使用個別的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6051a-118">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="6051a-119">如果您想要讓每一項使用個別 IP 位址，請選取核取方塊 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]**。</span><span class="sxs-lookup"><span data-stu-id="6051a-119">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**.</span></span> <span data-ttu-id="6051a-120">每個服務都必須有對應的 DNS 主機 (為它建立的) 記錄。</span><span class="sxs-lookup"><span data-stu-id="6051a-120">Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="6051a-121">針對每個對外服務，您可以指定 FQDN 和關聯的埠。</span><span class="sxs-lookup"><span data-stu-id="6051a-121">For each of the external-facing services, you specify a FQDN and an associated port.</span></span> <span data-ttu-id="6051a-122">例如， **SIP 存取** 將使用 sip.contoso.com 與關聯的埠5061。</span><span class="sxs-lookup"><span data-stu-id="6051a-122">For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6051a-123">如果您為每個對外的服務選取個別 FQDN，則每個服務必須有關聯的唯一連接埠值。</span><span class="sxs-lookup"><span data-stu-id="6051a-123">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="6051a-124">根據預設，SIP 位於埠5061/TLS 上，web 會議 edge service 位於埠444/TLS 上，而 A/V 會議伺服器位於埠443/TLS 上。</span><span class="sxs-lookup"><span data-stu-id="6051a-124">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="6051a-125">如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。</span><span class="sxs-lookup"><span data-stu-id="6051a-125">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="6051a-p106">如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]** 核取方塊。然後您就可以視需要編輯 **[SIP 存取]** 集區 FQDN 和連接埠值。</span><span class="sxs-lookup"><span data-stu-id="6051a-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6051a-128">如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。</span><span class="sxs-lookup"><span data-stu-id="6051a-128">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="6051a-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6051a-129">See also</span></span>

<span data-ttu-id="6051a-130">如需定義及設定 Edge Service 設定的詳細資訊，請參閱 [定義您的 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="6051a-130">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>