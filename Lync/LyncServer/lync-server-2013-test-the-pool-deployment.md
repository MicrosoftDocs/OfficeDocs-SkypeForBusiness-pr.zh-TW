---
title: Lync Server 2013： 測試集區部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46f656453b6ad6eee3eaf8fc0bbc8c26f308fe35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42019014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="55a76-102">在 Lync Server 2013 中測試集區部署</span><span class="sxs-lookup"><span data-stu-id="55a76-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55a76-103">_**上次修改主題：** 2013年-09-25_</span><span class="sxs-lookup"><span data-stu-id="55a76-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="55a76-104">下列程序說明如何測試部署的前端集區。</span><span class="sxs-lookup"><span data-stu-id="55a76-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="55a76-105">若要測試集區部署</span><span class="sxs-lookup"><span data-stu-id="55a76-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="55a76-106">將 Lync Server 2013 部署 （Lync Server 2013 控制台安裝所在） 中系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組使用 Active Directory 電腦和使用者。</span><span class="sxs-lookup"><span data-stu-id="55a76-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55a76-107">如果您未加入至 CsAdministors 群組新增適當的使用者和群組，您就會收到錯誤，當開啟 Lync Server Control Panel，表示 「 未授權： 存取被拒，因為角色型存取控制 (RBAC) 授權失敗。 」</span><span class="sxs-lookup"><span data-stu-id="55a76-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="55a76-108">如果使用者物件目前登入，請先登出，然後再次登入註冊新的群組指派。</span><span class="sxs-lookup"><span data-stu-id="55a76-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55a76-109">使用者帳戶不能執行 Lync Server 2013 的任何伺服器的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="55a76-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="55a76-110">使用系統管理帳戶來登入電腦已安裝 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="55a76-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="55a76-111">啟動 Lync Server 控制台]，並再提供認證，如果系統提示。</span><span class="sxs-lookup"><span data-stu-id="55a76-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="55a76-112">Lync Server Control Panel 顯示部署資訊。</span><span class="sxs-lookup"><span data-stu-id="55a76-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="55a76-113">在左的導覽列中，[**拓撲**]，然後確認服務狀態顯示帶有綠色箭頭的電腦，且每個已部署且上線的 Lync Server 伺服器角色旁邊為複寫狀態的綠色核取記號。</span><span class="sxs-lookup"><span data-stu-id="55a76-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="55a76-114">在左的導覽列中，按一下 [**使用者**]，然後按一下 [**啟用使用者**。</span><span class="sxs-lookup"><span data-stu-id="55a76-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="55a76-115">在 [**新增 Lync Server 使用者**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="55a76-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="55a76-116">若要定義搜尋參數，針對您想要尋找，請在 [**從 Active Directory 選取**] 頁面的物件您可以選取**搜尋**，然後 （選擇性) 按一下 [**新增篩選**。</span><span class="sxs-lookup"><span data-stu-id="55a76-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="55a76-117">您也可以選取 [ **LDAP 搜尋**，然後輸入 LDAP 運算式來篩選或限制將傳回的物件。</span><span class="sxs-lookup"><span data-stu-id="55a76-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="55a76-118">**尋找**您已決定搜尋選項之後，嗯。</span><span class="sxs-lookup"><span data-stu-id="55a76-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="55a76-119">在 [搜尋結果] 窗格中，針對此搜尋工作階段中，選取所有物件，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="55a76-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="55a76-120">在 [**新增 Lync Server 使用者**] 頁面或多個您所選取的物件是在**使用者**顯示。</span><span class="sxs-lookup"><span data-stu-id="55a76-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="55a76-121">在**指派使用者至集區**] 清單中，選取的伺服器應位於物件的位置。</span><span class="sxs-lookup"><span data-stu-id="55a76-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="55a76-122">以下是幾個設定物件的選項。</span><span class="sxs-lookup"><span data-stu-id="55a76-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="55a76-123">**產生使用者的 SIP URI**</span><span class="sxs-lookup"><span data-stu-id="55a76-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="55a76-124">**電話語音**</span><span class="sxs-lookup"><span data-stu-id="55a76-124">**Telephony**</span></span>
    
      - <span data-ttu-id="55a76-125">**線路 URI**</span><span class="sxs-lookup"><span data-stu-id="55a76-125">**Line URI**</span></span>
    
      - <span data-ttu-id="55a76-126">**會議原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="55a76-127">**用戶端版本原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="55a76-128">**Pin 碼原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="55a76-129">**外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-129">**External access policy**</span></span>
    
      - <span data-ttu-id="55a76-130">**封存原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="55a76-131">**位置原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-131">**Location policy**</span></span>
    
      - <span data-ttu-id="55a76-132">**用戶端原則**</span><span class="sxs-lookup"><span data-stu-id="55a76-132">**Client policy**</span></span>
    
    <span data-ttu-id="55a76-133">用於測試的基本功能的用途，請選取選項您要使用 [**產生使用者的 SIP URI** ] 設定 （在設定其他選項將會使用預設設定），然後按一下 [**啟用**。</span><span class="sxs-lookup"><span data-stu-id="55a76-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="55a76-134">摘要] 頁面上，會顯示，指出物件現在已準備好使用**已啟用**] 欄中會顯示一個核取記號。</span><span class="sxs-lookup"><span data-stu-id="55a76-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="55a76-135">[ **SIP 位址**] 欄中會顯示您需要的使用者登入設定地址。</span><span class="sxs-lookup"><span data-stu-id="55a76-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="55a76-136">一個使用者登入已加入網域的電腦並入另一部電腦的另一位使用者的網域中。</span><span class="sxs-lookup"><span data-stu-id="55a76-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="55a76-137">在每個兩部用戶端電腦上安裝 Lync 2013，然後確認 [兩個使用者可以登入 Lync Server 2013，並傳送立即訊息給對方。</span><span class="sxs-lookup"><span data-stu-id="55a76-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55a76-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55a76-138">See Also</span></span>


[<span data-ttu-id="55a76-139">部署用戶端和 Lync Server 2013 中的裝置</span><span class="sxs-lookup"><span data-stu-id="55a76-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

