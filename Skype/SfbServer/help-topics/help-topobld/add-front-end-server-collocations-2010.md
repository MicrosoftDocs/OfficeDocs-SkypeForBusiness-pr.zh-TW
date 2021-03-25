---
title: 新增前端伺服器組合 2010
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
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: 以 Enterprise Edition 部署而言，您可以將音訊/視訊會議服務、中繼伺服器或兩者都組合在前端集區上，或者，也可以將每一項各自部署為獨立伺服器。以 Standard Edition Server 部署而言，如果啟用會議，則一律會組合音訊/視訊會議服務。
ms.openlocfilehash: e9091a72d6909251a428ed7ee5273356eea387cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119752"
---
# <a name="add-front-end-server-collocations-2010"></a><span data-ttu-id="96bd2-104">新增前端伺服器組合 2010</span><span class="sxs-lookup"><span data-stu-id="96bd2-104">Add Front End Server Collocations 2010</span></span>

<span data-ttu-id="96bd2-p102">以 Enterprise Edition 部署而言，您可以將音訊/視訊會議服務、中繼伺服器或兩者都組合在前端集區上，或者，也可以將每一項各自部署為獨立伺服器。以 Standard Edition Server 部署而言，如果啟用會議，則一律會組合音訊/視訊會議服務。</span><span class="sxs-lookup"><span data-stu-id="96bd2-p102">For an Enterprise Edition deployment, you can collocate either the A/V Conferencing service, the Mediation Server, or both on the Front End pool, or you can deploy each as stand-alone servers. For a Standard Edition server deployment, the A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="96bd2-p103">如果在「選取功能」頁面上選取 [會議]，則需要音訊/視訊會議服務。Enterprise Edition 前端集區可以使用組合的音訊/視訊會議服務或獨立 A/V 會議集區。如果未選取 [會議]，則無法使用 [組合音訊/視訊會議服務]。</span><span class="sxs-lookup"><span data-stu-id="96bd2-p103">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page. An Enterprise Edition Front End pool may use a collocated A/V Conferencing service or a stand-alone A/V conferencing pool. If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="96bd2-110">您可以在 Standard Edition 前端伺服器或 Enterprise Edition 前端集區上組合中繼伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="96bd2-110">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="96bd2-111">如果您對支援媒體旁路和網域名稱系統 (DNS) 負載平衡的合格公用交換電話網路 (PSTN) 閘道部署了直接 SIP 連線，就不需要獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="96bd2-111">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="96bd2-112">因為合格閘道能夠將 DNS 負載平均分攤到中繼伺服器集區中，讓後者接收集區裡任何中繼伺服器的流量。</span><span class="sxs-lookup"><span data-stu-id="96bd2-112">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="96bd2-113">此外，當您已部署 IP-PBXs 或連線至網際網路電話語音伺服器提供者的會話邊界控制器 (SBC) 時，建議您在前端集區上組合轉送伺服器，只要符合下列任一條件：</span><span class="sxs-lookup"><span data-stu-id="96bd2-113">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="96bd2-114">IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。</span><span class="sxs-lookup"><span data-stu-id="96bd2-114">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="96bd2-115">IP-PBX 或 SBC 設定為接收集區中任何中繼伺服器的流量，並一律將流量傳送至集區中的所有中繼服務器。</span><span class="sxs-lookup"><span data-stu-id="96bd2-115">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="96bd2-116">您可以使用 Microsoft Lync Server 2013，規劃工具評估您想要組合轉送伺服器的前端集區是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="96bd2-116">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="96bd2-117">如果環境無法符合這些需求，則您必須部署獨立的中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="96bd2-117">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="96bd2-118">一般來說，如果您的組織具有高可用性和擴充性，組合的 A/V 會議伺服器或轉送伺服器，不建議使用此功能。若要在企業版部署的前端集區中組合這些伺服器角色，請參閱部署檔中的 [定義和設定前端集](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) 區。</span><span class="sxs-lookup"><span data-stu-id="96bd2-118">In general, collocation of A/V Conferencing Server or Mediation Server is not recommended if your organization has high availability and scalability requirementsFor details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span> <span data-ttu-id="96bd2-119">如需 A/V 會議功能和元件的詳細資訊，請參閱規劃文件中的＜[Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)＞。</span><span class="sxs-lookup"><span data-stu-id="96bd2-119">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span> <span data-ttu-id="96bd2-120">如需 Enterprise Voice 功能和元件（包括轉送伺服器）的詳細資訊，請參閱規劃檔中的在 [商務用 Skype Server 2015 中規劃 Enterprise Voice](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 。</span><span class="sxs-lookup"><span data-stu-id="96bd2-120">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>