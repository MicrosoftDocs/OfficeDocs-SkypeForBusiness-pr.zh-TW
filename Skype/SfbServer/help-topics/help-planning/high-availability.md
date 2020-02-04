---
title: 高可用性（規劃工具）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: 商務用 Skype Server 2015 中大多數伺服器角色的主要高可用性配置，都是透過 [彙集] 以伺服器冗余為基礎。 如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。
ms.openlocfilehash: 53b98b72c70fcb624ab59fc7bfc3fbffadbd231a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685436"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="135d9-104">高可用性（規劃工具）</span><span class="sxs-lookup"><span data-stu-id="135d9-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="135d9-105">商務用 Skype Server 2015 中大多數伺服器角色的主要高可用性配置，都是透過 [彙集] 以伺服器冗余為基礎。</span><span class="sxs-lookup"><span data-stu-id="135d9-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="135d9-106">如果執行特定伺服器角色的伺服器失敗，則池中執行相同角色的其他伺服器會載入該伺服器。</span><span class="sxs-lookup"><span data-stu-id="135d9-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="135d9-107">商務用 Skype Server 2015 需要至少兩個前端伺服器，才能啟用高可用性。</span><span class="sxs-lookup"><span data-stu-id="135d9-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="135d9-108">規劃工具會使用下列準則來判斷它是否會新增額外的伺服器，以支援高可用性：</span><span class="sxs-lookup"><span data-stu-id="135d9-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="135d9-109">如果部署包含兩個以上的前端伺服器，則規劃工具不會新增額外的伺服器。</span><span class="sxs-lookup"><span data-stu-id="135d9-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="135d9-110">如果部署包含 Edge 伺服器，則會新增其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="135d9-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="135d9-111">如果部署包含持續聊天，規劃工具將會新增額外的伺服器，但不會增加池的數目。</span><span class="sxs-lookup"><span data-stu-id="135d9-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="135d9-112">例如，如果部署已包含四個伺服器，則規劃工具會建議您新增其他伺服器（共5個伺服器），但會維持單一池。</span><span class="sxs-lookup"><span data-stu-id="135d9-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="135d9-113">規劃工具也會為所有資料庫新增鏡像 SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="135d9-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="135d9-114">例如，如果有前端 SQL Server 資料庫，規劃工具會將另一個資料庫作為此資料庫的鏡像資料庫，並將它命名為「前端鏡像 SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="135d9-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="135d9-115">如需有關如何針對高可用性準備環境的詳細資訊，請參閱[在商務用 Skype Server 2015 中規劃高可用性和災害復原](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="135d9-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

