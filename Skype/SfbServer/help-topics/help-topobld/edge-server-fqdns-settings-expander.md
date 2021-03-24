---
title: Edge Server FQDN 設定展開工具
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
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: 若要編輯或指定 Edge Server 的外部設定，您必須先決定是否要針對會話初始通訊協定使用個別的 IP 位址 (SIP) 存取、Web 會議 Edge service 及 Audio/Video Edge service。
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095558"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="b12c9-103">Edge Server FQDN 設定展開工具</span><span class="sxs-lookup"><span data-stu-id="b12c9-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="b12c9-104">若要編輯或指定 Edge Server 的 **外部設定** ，您必須先決定是否要針對會話初始通訊協定使用個別的 IP 位址 (SIP) 存取、Web 會議 Edge service 及 Audio/Video Edge service。</span><span class="sxs-lookup"><span data-stu-id="b12c9-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="b12c9-p101">如果您想要讓每一項使用個別 IP 位址，請選取核取方塊 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]**。每個服務必須已建立對應的網域名稱系統 (DNS) 主機 (A) 記錄。</span><span class="sxs-lookup"><span data-stu-id="b12c9-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="b12c9-p102">對於每個對外的服務，請指定完整網域名稱 (FQDN) 和關聯的連接埠。例如，在 **[SIP 存取]** 中，您可能使用 sip.contoso.com 和關聯的連接埠 5061。</span><span class="sxs-lookup"><span data-stu-id="b12c9-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b12c9-109">如果您為每個對外的服務選取個別 FQDN，則每個服務必須有關聯的唯一連接埠值。</span><span class="sxs-lookup"><span data-stu-id="b12c9-109">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="b12c9-110">根據預設，SIP 位於連接埠 5061/TLS、Web Conferencing Edge Service 位於連接埠 444/TLS，A/V Conferencing Edge Service 位於連接埠 443/TLS。</span><span class="sxs-lookup"><span data-stu-id="b12c9-110">By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS.</span></span> <span data-ttu-id="b12c9-111">如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。</span><span class="sxs-lookup"><span data-stu-id="b12c9-111">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="b12c9-p104">如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]** 核取方塊。然後您就可以視需要編輯 **[SIP 存取]** 集區 FQDN 和連接埠值。</span><span class="sxs-lookup"><span data-stu-id="b12c9-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b12c9-114">如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。</span><span class="sxs-lookup"><span data-stu-id="b12c9-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="b12c9-115">如需定義及設定 Edge service 設定的詳細資訊，請參閱 [定義您的 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。</span><span class="sxs-lookup"><span data-stu-id="b12c9-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>