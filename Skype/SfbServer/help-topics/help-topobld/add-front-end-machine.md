---
title: 新增前端機器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: 指定您要在此集區中，新增為前端伺服器之每台電腦的完整網域名稱 (FQDN)。 將電腦新增至清單後，您可以在發行拓撲之前，隨時更新電腦的 FQDN，或將它從集區移除。 發行拓撲之後，要變更 FQDN 便需要在拓撲產生器中刪除伺服器，然後用新的 FQDN 將新的伺服器新增到集區。 如需新增前端集區至拓撲的詳細資料，請參閱部署文件中的定義及設定前端集區。
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218314"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="566e9-106">新增前端機器</span><span class="sxs-lookup"><span data-stu-id="566e9-106">Add Front End Machine</span></span>

<span data-ttu-id="566e9-107">指定您要在此集區中，新增為前端伺服器之每台電腦的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="566e9-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="566e9-108">將電腦新增至清單後，您可以在發行拓撲之前，隨時更新電腦的 FQDN，或將它從集區移除。</span><span class="sxs-lookup"><span data-stu-id="566e9-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="566e9-109">發行拓撲之後，要變更 FQDN 便需要在拓撲產生器中刪除伺服器，然後用新的 FQDN 將新的伺服器新增到集區。</span><span class="sxs-lookup"><span data-stu-id="566e9-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="566e9-110">如需新增前端集區至拓撲的詳細資料，請參閱部署文件中的[定義及設定前端集區](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)。</span><span class="sxs-lookup"><span data-stu-id="566e9-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="566e9-111">請注意，拓撲產生器表示您最多可在集區中有20部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="566e9-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="566e9-112">支援的伺服器數目上限為12。</span><span class="sxs-lookup"><span data-stu-id="566e9-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="566e9-113">您最多可以有20個 statefull 伺服器定義在 fabric 中，其中12個可在任何時間使用中和線上。</span><span class="sxs-lookup"><span data-stu-id="566e9-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


