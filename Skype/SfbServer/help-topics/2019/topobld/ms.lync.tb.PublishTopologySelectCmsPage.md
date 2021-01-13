---
title: 發行拓撲選取 CMS 頁面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用拓撲產生器，發佈已設定的拓撲。 系統會要求您從清單中選取前端伺服器或前端集區，以擔當存放中央管理存放區的角色。 在任何指定時間，只有一部前端伺服器或前端集區可以持有此角色。
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822183"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="5ace3-105">發行拓撲選取 CMS 頁面</span><span class="sxs-lookup"><span data-stu-id="5ace3-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="5ace3-106">您可以使用拓撲產生器，發佈已設定的拓撲。</span><span class="sxs-lookup"><span data-stu-id="5ace3-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="5ace3-107">系統會要求您從清單中選取前端伺服器或前端集區，以擔當存放中央管理存放區的角色。</span><span class="sxs-lookup"><span data-stu-id="5ace3-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="5ace3-108">在任何指定時間，只有一部前端伺服器或前端集區可以持有此角色。</span><span class="sxs-lookup"><span data-stu-id="5ace3-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="5ace3-109">關於中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="5ace3-109">About the Central Management Server</span></span>
<span data-ttu-id="5ace3-110">中央管理伺服器是單一主/多個複本系統，其中包含中央管理伺服器的前端伺服器會持有資料庫的讀/寫副本。</span><span class="sxs-lookup"><span data-stu-id="5ace3-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="5ace3-111">拓撲中的每一部電腦（包括包含中央管理伺服器的前端伺服器）在安裝及部署期間，RTCLOCAL 會在電腦上安裝的預設) SQL Server (資料庫中的中央管理存放區資料的唯讀副本。</span><span class="sxs-lookup"><span data-stu-id="5ace3-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="5ace3-112">本機資料庫會透過 Lync Server 複本複製器代理程式，以在所有電腦上執行為服務的方式接收復本更新。</span><span class="sxs-lookup"><span data-stu-id="5ace3-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="5ace3-113">中央管理伺服器及本機複本上之實際資料庫的名稱是 XDS，這是由 XDS 及 XDS 檔所組成。</span><span class="sxs-lookup"><span data-stu-id="5ace3-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="5ace3-114">Master 資料庫位置是由 Active Directory 網域服務中 (SCP) 的服務控制點所參照。</span><span class="sxs-lookup"><span data-stu-id="5ace3-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="5ace3-115">所有使用中央管理伺服器來管理及設定 Lync Server 的工具，都使用 SCP 來尋找中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="5ace3-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5ace3-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5ace3-116">See also</span></span>

[<span data-ttu-id="5ace3-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="5ace3-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
