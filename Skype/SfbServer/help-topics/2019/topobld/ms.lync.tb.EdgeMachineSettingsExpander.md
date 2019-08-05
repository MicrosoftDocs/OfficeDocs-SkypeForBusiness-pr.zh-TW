---
title: Edge 電腦設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: '若要編輯 Edge 伺服器池中伺服器的屬性, 請執行下列動作:'
ms.openlocfilehash: a6683766ddbfd11cd38d2d50b80a25c057b302bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188974"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="c4f01-103">Edge 電腦設定擴展器</span><span class="sxs-lookup"><span data-stu-id="c4f01-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="c4f01-104">若要編輯 Edge 伺服器池中伺服器的屬性, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="c4f01-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="c4f01-105">您可以透過編輯完全限定的功能變數名稱 (FQDN) 來變更**內部名稱或 FQDN** 。</span><span class="sxs-lookup"><span data-stu-id="c4f01-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c4f01-106">FQDN 必須符合網域名稱系統 (DNS) 主機 (A) 記錄, 以及指派給內部 Edge 網路介面之伺服器之證書的消費者名稱。</span><span class="sxs-lookup"><span data-stu-id="c4f01-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="c4f01-107">**內部 IP 位址**的值定義指派為內部網路 (相對於周邊網路設計) 的網路介面的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="c4f01-108">此對話方塊的後三節定義此 Edge 伺服器的外部設定的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="c4f01-109">變更 IP 位址的能力受此設定在 Edge 伺服器池層級的屬性設定上**啟用不同的 FQDN 和 IP 位址與 A/V**的影響。</span><span class="sxs-lookup"><span data-stu-id="c4f01-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="c4f01-110">SIP 存取</span><span class="sxs-lookup"><span data-stu-id="c4f01-110">SIP Access</span></span>

<span data-ttu-id="c4f01-111">編輯指派給網路介面的外部 IP 位址, 以進行會話初始通訊協定 (SIP) 存取。</span><span class="sxs-lookup"><span data-stu-id="c4f01-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="c4f01-112">這個 IP 位址可以是公用 IP 位址或私人 IP 位址範圍中的位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4f01-113">如果啟用 [在 [緩衝集區設定] 頁面上,**啟用網頁會議與 A/V 的個別 FQDN 和 IP 位址**, 則只有 SIP 存取的 ip 位址可供編輯。</span><span class="sxs-lookup"><span data-stu-id="c4f01-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="c4f01-114">網路會議</span><span class="sxs-lookup"><span data-stu-id="c4f01-114">Web Conferencing</span></span>

<span data-ttu-id="c4f01-115">編輯指派給網路會議網路介面的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="c4f01-116">這個 IP 位址可以是公用 IP 位址或私人 IP 位址範圍中的位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="c4f01-117">音訊/視頻</span><span class="sxs-lookup"><span data-stu-id="c4f01-117">Audio/Video</span></span>

<span data-ttu-id="c4f01-118">編輯指派給音訊/視頻 (A/V) 網路介面的外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="c4f01-119">這個 IP 位址可以是公用 IP 位址或私人 IP 位址範圍中的位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="c4f01-120">**使用 NAT 啟用的公用 IP 位址**設定是外部介面 (一般是 A/V 網路介面或邊緣伺服器) 所使用的公用位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="c4f01-121">如果設定**啟用網路會議和 A/V 的個別 FQDN 和 IP 位址**, 則所有三個外部介面都會使用這個公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4f01-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

