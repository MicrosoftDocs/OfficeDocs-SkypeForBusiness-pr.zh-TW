---
title: 在商務用 Skype Server 中驗證拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '摘要: 瞭解如何驗證商務用 Skype 伺服器拓撲和 Active Directory 伺服器是否如預期運作。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: aad91c7bfb1e3187ace5d5caec4e3f18952a11d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193841"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="8ed0a-104">在商務用 Skype Server 中驗證拓撲</span><span class="sxs-lookup"><span data-stu-id="8ed0a-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="8ed0a-105">**摘要:** 瞭解如何驗證商務用 Skype 伺服器拓撲和 Active Directory 伺服器是否如預期運作。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="8ed0a-106">從[Microsoft 評估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下載商務用 Skype Server 的免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="8ed0a-107">在拓撲中發佈拓朴並安裝商務用 Skype Server system 元件之後, 您就可以開始確認拓朴是否如期運作。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="8ed0a-108">這包括驗證設定是否已傳播到所有的 Active Directory 伺服器, 讓整個網域在網域中都能知道商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="8ed0a-109">您可以依照任何循序執行步驟1到5。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="8ed0a-110">不過, 您必須在順序中執行步驟6、7和 8, 並在步驟1到5之後, 如圖表中所述。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="8ed0a-111">驗證拓撲是8的步驟8。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-111">Verifying the topology is step 8 of 8.</span></span>
  
![概覽圖表。](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="8ed0a-113">測試前端池部署</span><span class="sxs-lookup"><span data-stu-id="8ed0a-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="8ed0a-114">最後一個步驟是測試 [前端] 池, 並確認商務用 Skype 用戶端可以彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="8ed0a-115">新增使用者並驗證用戶端連線性</span><span class="sxs-lookup"><span data-stu-id="8ed0a-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="8ed0a-116">使用 Active Directory 電腦和使用者將商務用 Skype Server 部署 (在其中安裝商務用 Skype 伺服器控制台) 的系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8ed0a-117">如果您沒有將適當的使用者和群組新增至 CsAdministors 群組, 當您開啟商務用 Skype Server 的 [控制台] 時, 會收到錯誤訊息 [未授權]: 由於角色式存取控制 (RBAC) 授權失敗, 存取遭到拒絕."</span><span class="sxs-lookup"><span data-stu-id="8ed0a-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="8ed0a-118">如果使用者物件目前已登入, 請先登出後再登入, 以註冊新的群組指派。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8ed0a-119">使用者帳戶不能是執行商務用 Skype 伺服器的任何伺服器的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="8ed0a-120">使用系統管理帳戶登入已安裝商務用 Skype Server 控制台的電腦。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="8ed0a-121">啟動商務用 Skype Server 的 [控制台], 然後在出現提示時提供認證。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="8ed0a-122">商務用 Skype Server 的 [控制台] 會顯示部署資訊。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="8ed0a-123">在左側導覽列中, 按一下 [**拓撲**], 然後確認 [服務狀態] 會以綠色箭號顯示電腦, 且已部署並線上的每個商務用 Skype Server 角色旁邊都有綠色的核取記號。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="8ed0a-124">在左側導覽列中, 按一下 [**使用者**], 然後按一下 [**啟用使用者**]。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="8ed0a-125">在 [**新的商務用 Skype Server 使用者**] 頁面上, 按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="8ed0a-126">若要定義您想要尋找之物件的搜尋參數, 您可以在 [**從 Active Directory 中選取**] 頁面上選取 [**搜尋**], 然後按一下 [**新增篩選**] (選擇性)。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="8ed0a-127">您也可以選取 [ **ldap 搜尋**], 然後輸入 ldap 運算式來篩選或限制將傳回的物件。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="8ed0a-128">在您決定搜尋選項之後, 按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="8ed0a-129">在 [搜尋結果] 窗格中, 選取您要新增的使用者, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="8ed0a-130">在 [**新的商務用 Skype Server 使用者**] 頁面上, 您所選取的使用者會顯示在 [**使用者**] 顯示幕中。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="8ed0a-131">在 [**指派使用者至池中**] 清單中, 選取使用者應該駐留的伺服器。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="8ed0a-132">以下是您可以用來設定物件的選項清單。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="8ed0a-133">**產生使用者的 SIP URI**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="8ed0a-134">**$**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-134">**Telephony**</span></span>
    
    - <span data-ttu-id="8ed0a-135">**行 URI**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-135">**Line URI**</span></span>
    
    - <span data-ttu-id="8ed0a-136">**會議原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="8ed0a-137">**用戶端版本原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="8ed0a-138">**PIN 原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="8ed0a-139">**外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-139">**External access policy**</span></span>
    
    - <span data-ttu-id="8ed0a-140">**存檔原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="8ed0a-141">**位置原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-141">**Location policy**</span></span>
    
    - <span data-ttu-id="8ed0a-142">**用戶端原則**</span><span class="sxs-lookup"><span data-stu-id="8ed0a-142">**Client policy**</span></span>
    
    <span data-ttu-id="8ed0a-143">若要測試基本功能, 請在 [**產生使用者的 SIP URI** ] 設定 ([設定] 中的其他選項使用預設設定) 中, 選取您想要的選項, 然後按一下 [**啟用**], 如圖所示。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![在 [控制台] 中啟用使用者。](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="8ed0a-145">隨即會顯示 [摘要] 頁面, 其中顯示 [**已啟用**] 欄中的核取記號, 表示使用者已設定。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="8ed0a-146">[ **SIP 位址**] 欄會顯示使用者登入設定所需的位址。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![已將使用者新增至商務用 Skype Server 的 [控制台]。](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="8ed0a-148">將一位使用者登入加入網域的電腦, 以及另一個使用者到網域中的另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="8ed0a-149">在兩個用戶端電腦上安裝商務用 Skype 用戶端, 然後確認這兩個使用者都可以登入商務用 Skype Server, 並可互相傳送即時消息。</span><span class="sxs-lookup"><span data-stu-id="8ed0a-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

