---
title: Lync Server 2013：測試集區部署
description: Lync Server 2013：測試集區部署。
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
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576039"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="3c1a5-103">在 Lync Server 2013 中測試集區部署</span><span class="sxs-lookup"><span data-stu-id="3c1a5-103">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c1a5-104">_**主題上次修改日期：** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="3c1a5-104">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="3c1a5-105">下列程式說明如何測試前端集區的部署。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-105">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="3c1a5-106">測試集區部署</span><span class="sxs-lookup"><span data-stu-id="3c1a5-106">To test the pool deployment</span></span>

1.  <span data-ttu-id="3c1a5-107">使用 [Active Directory 電腦和使用者] 將 lync server 2013 部署 (的「系統管理員」角色的 Active Directory 使用者物件，新增至 **CSAdministrator** 群組) 安裝 lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3c1a5-108">如果您未將適當的使用者和群組新增至 CsAdministors 群組，當您開啟 Lync Server 控制台時，將會收到錯誤訊息，指出「未經授權：存取因角色型存取控制而拒絕 (RBAC) 授權失敗」。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-108">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="3c1a5-109">如果使用者物件目前已登入，請先登出再登入，以註冊新的群組指派。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-109">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c1a5-110">使用者帳戶不可以是執行 Lync Server 2013 之任何伺服器的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-110">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="3c1a5-111">使用系統管理帳戶登入安裝 Lync Server 控制台的電腦。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="3c1a5-112">啟動 Lync Server 控制台，然後在出現提示時提供認證。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-112">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="3c1a5-113">Lync Server 控制台會顯示部署資訊。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-113">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="3c1a5-114">在左導覽列中，按一下 [ **拓撲**]，然後確認服務狀態顯示具有綠色箭號的電腦，且每個已部署並聯機的 Lync server server role 旁都有綠色核取記號的副本狀態。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-114">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="3c1a5-115">在左導覽列中，按一下 [ **使用者**]，然後按一下 [ **啟用使用者**]。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-115">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="3c1a5-116">在 [ **新增 Lync Server 使用者** ] 頁面上 **，按一下 [新增]**。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-116">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="3c1a5-117">若要為您要尋找的物件定義搜尋參數，請在 [ **從 Active Directory 選取** ] 頁面上，選取 [ **搜尋**]，然後選擇性地按一下 [ **新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-117">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="3c1a5-118">您也可以選取 [ **ldap 搜尋** ] 並輸入 ldap 運算式，以篩選或限制將要傳回的物件。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-118">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="3c1a5-119">在您決定搜尋選項之後，請 clink **Find**。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-119">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="3c1a5-120">在 [搜尋結果] 窗格中，選取此搜尋會話的所有物件，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-120">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="3c1a5-121">在 [ **新增 Lync Server 使用者** ] 頁面上，您所選取的物件會顯示在 [ **使用者** ] 中。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-121">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="3c1a5-122">在 [ **指派使用者至集** 區] 清單中，選取物件應該駐留的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-122">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="3c1a5-123">以下是設定物件的一些選項。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-123">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="3c1a5-124">**產生使用者的 SIP URI**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-124">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="3c1a5-125">**電話**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-125">**Telephony**</span></span>
    
      - <span data-ttu-id="3c1a5-126">**行 URI**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-126">**Line URI**</span></span>
    
      - <span data-ttu-id="3c1a5-127">**會議原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-127">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="3c1a5-128">**用戶端版本原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-128">**Client version policy**</span></span>
    
      - <span data-ttu-id="3c1a5-129">**PIN 原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-129">**PIN policy**</span></span>
    
      - <span data-ttu-id="3c1a5-130">**外部存取原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-130">**External access policy**</span></span>
    
      - <span data-ttu-id="3c1a5-131">**封存原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-131">**Archiving policy**</span></span>
    
      - <span data-ttu-id="3c1a5-132">**位置原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-132">**Location policy**</span></span>
    
      - <span data-ttu-id="3c1a5-133">**用戶端原則**</span><span class="sxs-lookup"><span data-stu-id="3c1a5-133">**Client policy**</span></span>
    
    <span data-ttu-id="3c1a5-134">針對測試基本功能的目的，請選取您想要用於 [ **產生使用者的 SIP URI** ] 設定的選項 (設定中的其他選項將使用預設設定) ，然後按一下 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-134">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="3c1a5-135">顯示 [摘要] 頁面，在 [ **已啟用** ] 欄中顯示核取記號，表示物件現在可以使用。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-135">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="3c1a5-136">[ **SIP 位址** ] 欄會顯示使用者登入設定所需的位址。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-136">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="3c1a5-137">將一個使用者登入已加入網域的電腦，並將另一個使用者登入網域中的另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-137">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="3c1a5-138">在兩部用戶端電腦上安裝 Lync 2013，然後確認這兩位使用者皆可登入 Lync Server 2013，而且可以相互傳送立即訊息。</span><span class="sxs-lookup"><span data-stu-id="3c1a5-138">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c1a5-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3c1a5-139">See Also</span></span>


[<span data-ttu-id="3c1a5-140">在 Lync Server 2013 中部署用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="3c1a5-140">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

