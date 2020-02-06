---
title: 發行拓撲選取 CMS 頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 您可以使用 [拓撲建立器] 發佈已設定的拓撲。 系統會要求您從清單中選取前端伺服器或前端池將會擔任中央管理儲存區的角色。 在任何指定時間，只有一個前端伺服器或前端池可以擁有此角色。
ms.openlocfilehash: cae0f79b9787458ae1dd24077dfdd46689378414
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795414"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="80d81-105">發行拓撲選取 CMS 頁面</span><span class="sxs-lookup"><span data-stu-id="80d81-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="80d81-106">您可以使用 [拓撲建立器] 發佈已設定的拓撲。</span><span class="sxs-lookup"><span data-stu-id="80d81-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="80d81-107">系統會要求您從清單中選取前端伺服器或前端池將會擔任中央管理儲存區的角色。</span><span class="sxs-lookup"><span data-stu-id="80d81-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="80d81-108">在任何指定時間，只有一個前端伺服器或前端池可以擁有此角色。</span><span class="sxs-lookup"><span data-stu-id="80d81-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="80d81-109">關於中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="80d81-109">About the Central Management Server</span></span>
<span data-ttu-id="80d81-110">[中央管理伺服器] 是單一主要/多重複本系統，其中資料庫的讀/寫複本是由包含中央管理伺服器的前端伺服器所保留。</span><span class="sxs-lookup"><span data-stu-id="80d81-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="80d81-111">拓朴中的每個電腦（包括包含中央管理伺服器的前端伺服器）在安裝期間都有在電腦上安裝的 SQL Server 資料庫中的中央管理儲存資料（預設為 RTCLOCAL）的唯讀複本部署.</span><span class="sxs-lookup"><span data-stu-id="80d81-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="80d81-112">本機資料庫會按照 Lync Server 複本複製器代理程式（在所有電腦上以服務形式執行）的方式來接收復制副本更新。</span><span class="sxs-lookup"><span data-stu-id="80d81-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="80d81-113">中央管理伺服器上的實際資料庫名稱與局部複本是 XDS，這是由 XDS 和 XDS 檔案組成。</span><span class="sxs-lookup"><span data-stu-id="80d81-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="80d81-114">主資料庫位置是由 Active Directory 網域服務中的服務控制點（SCP）所參照。</span><span class="sxs-lookup"><span data-stu-id="80d81-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="80d81-115">所有使用中央管理伺服器來管理和設定 Lync Server 的工具，都使用 SCP 來尋找中央管理儲存區。</span><span class="sxs-lookup"><span data-stu-id="80d81-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80d81-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="80d81-116">See also</span></span>

[<span data-ttu-id="80d81-117">移動流覽 CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="80d81-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
