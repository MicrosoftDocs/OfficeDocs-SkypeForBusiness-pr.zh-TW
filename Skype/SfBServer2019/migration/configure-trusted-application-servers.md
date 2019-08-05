---
title: 設定受信任的應用程式伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在混合式環境中, 如果您建立新的受信任的應用程式伺服器, 您必須將下一個躍點池設定為商務用 Skype Server 2019 池。 在混合式環境中, 舊版文件庫和商務用 Skype Server 2019 池都會出現在下拉式清單中。 不支援選取舊版池。
ms.openlocfilehash: b0dfb9ba1e4744ba3e0ea0c376f67a224e70376a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191557"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="233ee-105">設定受信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="233ee-105">Configure trusted application servers</span></span>

<span data-ttu-id="233ee-106">在混合式環境中, 如果您建立新的受信任的應用程式伺服器, 您必須將下一個躍點池設定為商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="233ee-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="233ee-107">在混合式環境中, 舊版文件庫和商務用 Skype Server 2019 池都會出現在下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="233ee-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="233ee-108">不支援選取舊版池。</span><span class="sxs-lookup"><span data-stu-id="233ee-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="233ee-109">如果您要遷移受信任的應用程式伺服器, 您也應該更新您正在使用的 UCMA 版本。</span><span class="sxs-lookup"><span data-stu-id="233ee-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="233ee-110">如果您為商務用 Skype Server 2019 建立新的受信任的應用程式池, 您應該更新 UCMA 至商務用 Skype Server 2019 隨附的版本或最新版本。</span><span class="sxs-lookup"><span data-stu-id="233ee-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="233ee-111">在建立信任的應用程式伺服器時, 選取 [商務用 Skype Server 2019] 作為下一個躍點</span><span class="sxs-lookup"><span data-stu-id="233ee-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="233ee-112">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="233ee-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="233ee-113">在左窗格中, 以滑鼠右鍵按一下 [**信任的應用程式伺服器**], 然後按一下 [**新增信任的應用程式池**]</span><span class="sxs-lookup"><span data-stu-id="233ee-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="233ee-114">輸入受信任的應用程式池的 [**池 FQDN** ], 然後選取它將是單一伺服器或多重伺服器。</span><span class="sxs-lookup"><span data-stu-id="233ee-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="233ee-115">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="233ee-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="233ee-116">在 [**選取下一個躍點]** 頁面上的清單中, 選取 [商務用 Skype Server 2019 前端] 池。</span><span class="sxs-lookup"><span data-stu-id="233ee-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="233ee-117">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="233ee-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="233ee-118">選取最上層**的商務用 Skype 伺服器**, 然後從 [**動作**] 功能表中選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="233ee-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="233ee-119">確認信任的**應用程式池**已順利建立, 且與正確的 [前端] 池相關聯。</span><span class="sxs-lookup"><span data-stu-id="233ee-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

