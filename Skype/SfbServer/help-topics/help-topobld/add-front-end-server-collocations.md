---
title: 新增前端伺服器組合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: 在企業版部署中，A/V 會議服務是在前端池中 collocated。 您也可以在前端池中 collocate 轉送伺服器，或將它部署為獨立伺服器。 如果已啟用會議，A/V 會議服務就會一直 collocated。
ms.openlocfilehash: 0d246e91549f5ff27a2e3681aae4d73c064eb67c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698208"
---
# <a name="add-front-end-server-collocations"></a><span data-ttu-id="5c34d-105">新增前端伺服器組合</span><span class="sxs-lookup"><span data-stu-id="5c34d-105">Add Front End Server Collocations</span></span>

<span data-ttu-id="5c34d-106">在企業版部署中，A/V 會議服務是在前端池中 collocated。</span><span class="sxs-lookup"><span data-stu-id="5c34d-106">For an Enterprise Edition deployment, the A/V Conferencing service is collocated on the Front End pool.</span></span> <span data-ttu-id="5c34d-107">您也可以在前端池中 collocate 轉送伺服器，或將它部署為獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c34d-107">You can also collocate the Mediation Server on the Front End pool, or you can deploy it as a stand-alone server.</span></span> <span data-ttu-id="5c34d-108">如果已啟用會議，A/V 會議服務就會一直 collocated。</span><span class="sxs-lookup"><span data-stu-id="5c34d-108">The A/V Conferencing service is always collocated if conferencing is enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="5c34d-109">如果在 [**選取功能**] 頁面上選取 [**會議**]，就必須有 A/V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="5c34d-109">An A/V Conferencing service is required if **Conferencing** was selected on the **Select features** page.</span></span> <span data-ttu-id="5c34d-110">「企業版」前端池使用 collocated A/V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="5c34d-110">An Enterprise Edition Front End pool uses a collocated A/V Conferencing service.</span></span> <span data-ttu-id="5c34d-111">如果未選取 [會議]，將無法使用 Collocate A/V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="5c34d-111">If Conferencing was not selected, the Collocate A/V Conferencing service will not be available.</span></span>

<span data-ttu-id="5c34d-112">您可以 collocate 標準版前端伺服器或企業版前端池的中繼伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="5c34d-112">You can collocate the Mediation Server role on a Standard Edition Front End Server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="5c34d-113">如果您將直接 SIP 連線部署到支援媒體旁路和網域名稱系統（DNS）負載平衡的合格公用交換電話網絡（PSTN）閘道，則不需要獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="5c34d-113">If you deploy Direct SIP connections to a qualified public switched telephone network (PSTN) gateway that supports media bypass and Domain Name System (DNS) load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="5c34d-114">不需要獨立的吸入式伺服器池，因為合格的閘道能夠將 DNS 負載平衡傳送到中繼伺服器的池中，而且可以從池中的任何中繼伺服器接收流量。</span><span class="sxs-lookup"><span data-stu-id="5c34d-114">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span> <span data-ttu-id="5c34d-115">我們也建議您在已部署 IP Pbx 或連線至網際網路電話語音器提供者的會話邊界控制器（SBC）時，在前端池中 collocate 轉送伺服器，只要符合下列任何一個條件：</span><span class="sxs-lookup"><span data-stu-id="5c34d-115">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider's Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

- <span data-ttu-id="5c34d-116">IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c34d-116">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

- <span data-ttu-id="5c34d-117">IP PBX 或 SBC 已設定為從池中的任何中繼伺服器接收流量，並可將流量統一傳送給池中的所有中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c34d-117">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

<span data-ttu-id="5c34d-118">您可以使用 Microsoft Lync Server 2013、規劃工具來評估您要 collocate 中繼伺服器的前端池是否可以處理負載。</span><span class="sxs-lookup"><span data-stu-id="5c34d-118">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="5c34d-119">如果您的環境無法符合這些需求，則您必須部署獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="5c34d-119">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="5c34d-120">一般來說，如果您的組織有高可用性和伸縮性需求，則不建議使用 collocation 伺服器的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c34d-120">In general, collocation of Mediation Server is not recommended if your organization has high availability and scalability requirements.</span></span> <span data-ttu-id="5c34d-121">如需在企業版部署的前端池中 collocating 這些伺服器角色的詳細資料，請參閱在部署檔中[定義及設定前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5c34d-121">For details about collocating these server roles in a Front End pool in an Enterprise Edition deployment, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="5c34d-122">如需 A/V 會議功能與元件的詳細資料，請參閱規劃檔中的[會議規劃](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5c34d-122">For details about the A/V Conferencing feature and components, see [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5c34d-123">如需企業語音功能與元件（包括轉送伺服器）的詳細資料，請參閱規劃檔中的[商務用 Skype Server 2015 中的企業語音規劃](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="5c34d-123">For details about Enterprise Voice features and components, including Mediation Server, see [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.</span></span>


