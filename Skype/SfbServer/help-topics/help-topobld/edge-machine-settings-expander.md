---
title: Edge 電腦設定展開工具
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
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 若要編輯 Edge Server 集區中某個伺服器的內容，請執行下列動作：
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807123"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="186cd-103">Edge 電腦設定展開工具</span><span class="sxs-lookup"><span data-stu-id="186cd-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="186cd-104">若要編輯 Edge Server 集區中某個伺服器的內容，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="186cd-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="186cd-p101">您可以編輯完整網域名稱 (FQDN) 來變更 [內部名稱或 FQDN]。FQDN 必須符合網域名稱系統 (DNS) 主機 (A) 記錄以及憑證 (指派給內部 Edge 網路介面的伺服器) 的主體名稱。[內部 IP 位址] 的值定義 IP 位址，此位址被指派已定義為內部網路的網路介面 (相對於周邊網路設計)。</span><span class="sxs-lookup"><span data-stu-id="186cd-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="186cd-p102">對話方塊接下來三個區段定義此 Edge Server 的外部組態的 IP 位址。是否有能力變更 IP 位址，取決於 Edge Server 集區層級的 [內容] 設定上的 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址] 設定。</span><span class="sxs-lookup"><span data-stu-id="186cd-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="186cd-110">SIP 存取</span><span class="sxs-lookup"><span data-stu-id="186cd-110">SIP Access</span></span>

<span data-ttu-id="186cd-p103">編輯外部 IP 位址，以指派給工作階段初始通訊協定 (SIP) 存取的網路介面。此 IP 位址可以是公用 IP 位址或是私人 IP 位址範圍中的位址。</span><span class="sxs-lookup"><span data-stu-id="186cd-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="186cd-113">如果集區設定頁面上的 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址] 設定已啟用，則只能編輯 SIP 存取的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="186cd-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="186cd-114">Web 會議</span><span class="sxs-lookup"><span data-stu-id="186cd-114">Web Conferencing</span></span>

<span data-ttu-id="186cd-p104">編輯外部 IP 位址，以指派給 Web 會議的網路介面。此 IP 位址可以是公用 IP 位址或是私人 IP 位址範圍中的位址。</span><span class="sxs-lookup"><span data-stu-id="186cd-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="186cd-117">Audio/Video</span><span class="sxs-lookup"><span data-stu-id="186cd-117">Audio/Video</span></span>

<span data-ttu-id="186cd-p105">編輯外部 IP 位址，以指派給音訊/視訊 (A/V) 的網路介面。此 IP 位址可以是公用 IP 位址或是私人 IP 位址範圍中的位址。</span><span class="sxs-lookup"><span data-stu-id="186cd-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="186cd-p106">[已使用啟用 NAT 的公用 IP 位址] 的設定，通常是由 A/V 網路介面或 Edge Server 的外部介面所使用的公用位址。如果 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址] 已啟用，則三個外部介面全部都會使用此公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="186cd-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

