---
title: 定義常設聊天室集區的屬性和選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 您可以透過定義下列屬性來設定持續聊天伺服器或持續聊天伺服器池的選項：
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697548"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="c6a04-103">定義常設聊天室集區的屬性和選項</span><span class="sxs-lookup"><span data-stu-id="c6a04-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="c6a04-104">您可以透過定義下列屬性來設定持續聊天伺服器或持續聊天伺服器池的選項：</span><span class="sxs-lookup"><span data-stu-id="c6a04-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="c6a04-105">**[持續式聊天] 池的顯示名稱**： [必要] 屬性定義將針對此持續聊天伺服器或持久聊天伺服器池顯示的使用者易記名稱。</span><span class="sxs-lookup"><span data-stu-id="c6a04-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="c6a04-106">**持續聊天埠**：將會定義此持續聊天伺服器或持久聊天伺服器池將接聽之埠號碼的必要屬性。</span><span class="sxs-lookup"><span data-stu-id="c6a04-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="c6a04-107">**啟用合規性**：如果您打算部署並執行選用的持續聊天合規性功能和資料庫，請選取該核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c6a04-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="c6a04-108">**使用備份 SQL Server 存儲區來啟用災難**復原：如果您打算從已設定的另一個 SQL server 商店備份組，請選取此核取方塊，以將持續聊天 SQL server 存儲區的災難復原部署並執行。</span><span class="sxs-lookup"><span data-stu-id="c6a04-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="c6a04-109">如需詳細資訊，請參閱[在商務用 Skype server 2015 中設定持續聊天伺服器的高可用性和災害復原](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a04-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6a04-110">這個選項只適用於具有多部伺服器的集區。</span><span class="sxs-lookup"><span data-stu-id="c6a04-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="c6a04-111">**使用此 pool 作為此伺服器或文檔\<庫正在進行設定\>的網站網站的預設值**：如果這是該網站的預設持續聊天伺服器或持續聊天伺服器池，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c6a04-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="c6a04-112">每個網站必須有一個預設持續聊天伺服器或 pol。</span><span class="sxs-lookup"><span data-stu-id="c6a04-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6a04-113">如果拓撲包含多個網站，也會顯示 [使用此集區作為所有網站的預設值]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c6a04-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="c6a04-114">按 [上一步]\*\*\*\* 回到上一個集區定義對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c6a04-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="c6a04-115">完成輸入此池子的選項後，請按 **[下一步]** ，繼續進行持續聊天伺服器池的定義。</span><span class="sxs-lookup"><span data-stu-id="c6a04-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="c6a04-116">按一下 [取消]\*\*\*\* 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6a04-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="c6a04-117">按一下 [說明]\*\*\*\* 存取即時線上說明，例如此頁面。</span><span class="sxs-lookup"><span data-stu-id="c6a04-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c6a04-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6a04-118">See also</span></span>

[<span data-ttu-id="c6a04-119">在商務用 Skype Server 2015 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="c6a04-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="c6a04-120">在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器</span><span class="sxs-lookup"><span data-stu-id="c6a04-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
