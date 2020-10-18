---
title: Lync Server 2013：測試 Standard Edition Server
description: Lync Server 2013：測試 Standard Edition Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35dc13fc01979cc8b293d0647a7886b7d65d7669
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576007"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f5f70-103">在 Lync Server 2013 中測試 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="f5f70-103">Test the Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5f70-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f5f70-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f5f70-105">下列程式說明如何測試 Standard Edition server 的部署。</span><span class="sxs-lookup"><span data-stu-id="f5f70-105">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="f5f70-106">若要測試 Standard Edition Server 的部署</span><span class="sxs-lookup"><span data-stu-id="f5f70-106">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="f5f70-107">使用 [Active Directory 電腦和使用者] 將 lync server 2013 部署 (的系統管理員角色的 Active Directory 使用者物件，加入) **CSAdministrator** 群組中的「安裝 lync Server」控制台。</span><span class="sxs-lookup"><span data-stu-id="f5f70-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="f5f70-108">如果使用者物件目前已登入，請先登出再登入，以註冊新的群組指派。</span><span class="sxs-lookup"><span data-stu-id="f5f70-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5f70-109">使用者帳戶不可以是執行 Lync Server 2013，Standard Edition 之伺服器的本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f5f70-109">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="f5f70-110">如果您未將適當的使用者和群組新增至 CsAdministors 群組，當您開啟 Lync Server 2013 控制台時，將會收到錯誤訊息，指出「未經授權：存取因角色型的存取控制 (RBAC) 授權失敗」而遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="f5f70-110">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="f5f70-111">使用系統管理帳戶登入安裝 Lync Server 控制台的電腦。</span><span class="sxs-lookup"><span data-stu-id="f5f70-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="f5f70-112">啟動 Lync Server 控制台，並在出現提示時提供認證。</span><span class="sxs-lookup"><span data-stu-id="f5f70-112">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="f5f70-113">Lync Server 2013 控制台會顯示部署資訊。</span><span class="sxs-lookup"><span data-stu-id="f5f70-113">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="f5f70-114">在左導覽列中，按一下 [ **拓撲**]，然後確認服務狀態是具有綠色箭頭的電腦圖示，且每個已部署並聯機的 Lync server server role 旁邊都有綠色核取記號。</span><span class="sxs-lookup"><span data-stu-id="f5f70-114">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="f5f70-115">在左導覽列中，按一下 [ **使用者**]，然後啟用兩個使用者的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f5f70-115">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="f5f70-116">將一個使用者登入已加入網域的電腦，並將另一個使用者登入網域中的另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="f5f70-116">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="f5f70-117">在兩部用戶端電腦上安裝 Lync Server 2013，然後確認這兩位使用者皆可登入 Lync Server 2013，而且可以傳送立即訊息給對方。</span><span class="sxs-lookup"><span data-stu-id="f5f70-117">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5f70-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5f70-118">See Also</span></span>


[<span data-ttu-id="f5f70-119">在 Lync Server 2013 中部署用戶端和裝置</span><span class="sxs-lookup"><span data-stu-id="f5f70-119">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

