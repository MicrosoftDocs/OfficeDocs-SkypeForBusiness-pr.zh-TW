---
title: Edge 設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯一或多個現有服器 Edge 集區的設定，請參考下列區段：
ms.openlocfilehash: 02ee1db9019e6a12b9c166cbb766e8a90ac55da2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189193"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="9df2b-103">Edge 設定展開工具</span><span class="sxs-lookup"><span data-stu-id="9df2b-103">Edge Settings Expander</span></span>

<span data-ttu-id="9df2b-104">若要編輯一或多個現有服器 Edge 集區的設定，請參考下列區段：</span><span class="sxs-lookup"><span data-stu-id="9df2b-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="9df2b-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="9df2b-105">General settings</span></span>

- <span data-ttu-id="9df2b-106">下一個躍點選取範圍設定</span><span class="sxs-lookup"><span data-stu-id="9df2b-106">Next hop selection settings</span></span>

- <span data-ttu-id="9df2b-107">Edge Server 組態</span><span class="sxs-lookup"><span data-stu-id="9df2b-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="9df2b-108">一般設定</span><span class="sxs-lookup"><span data-stu-id="9df2b-108">General settings</span></span>

<span data-ttu-id="9df2b-p101">Edge Server 集區的內部集區完整網域名稱 (FQDN)。編輯集區的 FQDN 以變更此設定。</span><span class="sxs-lookup"><span data-stu-id="9df2b-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="9df2b-111">如果您要設定與商務用 Skype Server 2015 伺服器的同盟, 請選取 [**針對此 Edge 池啟用同盟 (埠 5061)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9df2b-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="9df2b-112">指定 [內部組態複寫連接埠 (HTTPS)]\*\*\*\* 的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="9df2b-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="9df2b-113">下一個躍點選取範圍設定</span><span class="sxs-lookup"><span data-stu-id="9df2b-113">Next hop selection settings</span></span>

<span data-ttu-id="9df2b-114">若要設定或修改 Edge Server 用來與內部基礎結構進行通訊的 [下一個躍點集區]\*\*\*\*，請從下拉式清單方塊中，選取 Director、Director 集區、前端伺服器或前端伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="9df2b-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="9df2b-115">只有已在拓撲結構建立器中設定的控制器或端點會顯示選取範圍。</span><span class="sxs-lookup"><span data-stu-id="9df2b-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="9df2b-116">Edge Server 組態</span><span class="sxs-lookup"><span data-stu-id="9df2b-116">Edge Server configuration</span></span>

<span data-ttu-id="9df2b-117">若要為 Edge Server 編輯或指定 [外部設定]\*\*\*\* 的相關設定，必須先判定是否要針對 SIP 存取、Web 會議與音訊/視訊服務使用個別的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="9df2b-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="9df2b-p103">如果您想要讓每一項使用個別 IP 位址，請選取 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]\*\*\*\*。每一項服務必須具有專為其建立的對應 DNS 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="9df2b-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="9df2b-p104">您必須針對每一個對外服務指定 FQDN 以及相關聯的連接埠。例如，[SIP 存取]\*\*\*\* 會使用 sip.contoso.com 以及相關聯的連接埠 5061。</span><span class="sxs-lookup"><span data-stu-id="9df2b-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9df2b-p105">如果您為每個對外的服務選取個別 FQDN，則每個服務必須有相關聯的唯一連接埠值。根據預設，SIP 位於連接埠 5061/TLS，Web Conferencing Edge Service 則位於連接埠 444/TLS，而 A/V 會議伺服器則位於連接埠 443/TLS。如果您變更以上任何設定，包括使用個別 FQDN 和 IP 位址或連接埠，即必須更新依賴初始設定值的所有其他服務。</span><span class="sxs-lookup"><span data-stu-id="9df2b-p105">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="9df2b-p106">如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]\*\*\*\* 核取方塊。接著就可以根據需要，編輯 [SIP 存取]\*\*\*\* 集區 FQDN 和連接埠值。</span><span class="sxs-lookup"><span data-stu-id="9df2b-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9df2b-127">如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或連接埠，您必須更新其他所有依賴初始設定值的服務。</span><span class="sxs-lookup"><span data-stu-id="9df2b-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="9df2b-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9df2b-128">See also</span></span>

<span data-ttu-id="9df2b-129">如需詳細瞭解定義和設定 Edge Service 的設定，請參閱〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="9df2b-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


