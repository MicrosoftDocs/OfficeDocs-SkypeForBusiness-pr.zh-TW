---
title: '高可用性 (規劃工具) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: 商務用 Skype Server 中大多數伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。 如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093311"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="dbe69-104">高可用性 (規劃工具) </span><span class="sxs-lookup"><span data-stu-id="dbe69-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="dbe69-105">商務用 Skype Server 中大多數伺服器角色的主要高可用性架構，都是透過 pooling server 冗余度為基礎。</span><span class="sxs-lookup"><span data-stu-id="dbe69-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="dbe69-106">如果執行特定伺服器角色的伺服器失敗，集區中執行相同角色的其他伺服器就會接手該伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="dbe69-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="dbe69-107">商務用 Skype Server 至少需要兩部前端伺服器才能啟用高可用性。</span><span class="sxs-lookup"><span data-stu-id="dbe69-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="dbe69-108">規劃工具使用下列準則來判斷是否會加入額外的伺服器，以支援高可用性：</span><span class="sxs-lookup"><span data-stu-id="dbe69-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="dbe69-109">如果部署包含兩部以上的前端伺服器，則規劃工具不會新增額外的伺服器。</span><span class="sxs-lookup"><span data-stu-id="dbe69-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="dbe69-110">如果部署包含 Edge Server，則會新增額外的伺服器。</span><span class="sxs-lookup"><span data-stu-id="dbe69-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="dbe69-111">如果部署包含持續性聊天，規劃工具將會新增額外的伺服器，但不會增加集區數目。</span><span class="sxs-lookup"><span data-stu-id="dbe69-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="dbe69-112">例如，如果部署已包含四部伺服器，則規劃工具會建議您新增額外的伺服器 (，讓總數超過5部伺服器) ，但會維護單一集區。</span><span class="sxs-lookup"><span data-stu-id="dbe69-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="dbe69-113">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="dbe69-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="dbe69-114">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="dbe69-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="dbe69-115">如需詳細資訊，請參閱 [商務用 Skype To Microsoft 小組升級](/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="dbe69-115">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="dbe69-116">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="dbe69-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="dbe69-117">規劃工具也會為所有資料庫新增鏡像 SQL 資料庫。</span><span class="sxs-lookup"><span data-stu-id="dbe69-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="dbe69-118">例如，如果有前端 SQL Server 資料庫，規劃工具會將另一個資料庫新增為此資料庫的鏡像資料庫，並將其命名為「前端鏡像 SQL 資料庫」。</span><span class="sxs-lookup"><span data-stu-id="dbe69-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="dbe69-119">如需準備環境以取得高可用性的詳細資訊，請參閱 [在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="dbe69-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
