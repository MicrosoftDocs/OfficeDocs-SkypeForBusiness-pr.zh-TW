---
title: 新增前端機器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: 指定您想要在此池中新增為前端伺服器的每個電腦的完整功能變數名稱（FQDN）。 將電腦新增至清單後，即可更新電腦的 FQDN，或在發行拓撲前，隨時將它從集區中移除。 發佈拓撲之後，變更 FQDN 需要先刪除拓撲建立器中的伺服器，然後使用新的 FQDN 將新的伺服器新增到該池。 如需將 [前端] 池新增到拓撲中的詳細資料，請參閱在部署檔中定義及設定前端池。
ms.openlocfilehash: a11042c8d91089e74ab1bacfc5206eb7d2fa3f67
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689303"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="a76c2-106">新增前端機器</span><span class="sxs-lookup"><span data-stu-id="a76c2-106">Add Front End Machine</span></span>

<span data-ttu-id="a76c2-107">指定您想要在此池中新增為前端伺服器的每個電腦的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="a76c2-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="a76c2-108">將電腦新增至清單後，即可更新電腦的 FQDN，或在發行拓撲前，隨時將它從集區中移除。</span><span class="sxs-lookup"><span data-stu-id="a76c2-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="a76c2-109">發佈拓撲之後，變更 FQDN 需要先刪除拓撲建立器中的伺服器，然後使用新的 FQDN 將新的伺服器新增到該池。</span><span class="sxs-lookup"><span data-stu-id="a76c2-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="a76c2-110">如需將 [前端] 池新增到拓撲中的詳細資料，請參閱在部署檔中[定義及設定前端池](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a76c2-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a76c2-111">請注意，拓撲建立器表示您最多可以在一個池中擁有20個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="a76c2-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="a76c2-112">支援的伺服器數目上限為12個。</span><span class="sxs-lookup"><span data-stu-id="a76c2-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="a76c2-113">您最多可以在結構中定義20個 statefull 伺服器，其中12個可在任何時間使用中且在線上。</span><span class="sxs-lookup"><span data-stu-id="a76c2-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


