---
title: 還原鏡像的 Enterprise Edition 後端伺服器-鏡像
description: 還原鏡像的 Enterprise Edition 後端伺服器-鏡像。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 011c0aaa10ffed6fef7d579dbc16993fd3341070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543799"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="68f3d-103">在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-鏡像</span><span class="sxs-lookup"><span data-stu-id="68f3d-103">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f3d-104">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="68f3d-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="68f3d-105">如果您在鏡像設定中有 Enterprise Edition 後端伺服器，且只有鏡像失敗，請遵循本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="68f3d-105">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="68f3d-106">如果主資料庫和鏡像都失敗，請參閱 [在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="68f3d-106">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="68f3d-107">若只有主要的失敗，請參閱 [在 Lync server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。</span><span class="sxs-lookup"><span data-stu-id="68f3d-107">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="68f3d-108">若主控中央管理存放區的資料庫失敗，請參閱 [在 Lync server 2013 中還原主控中央管理存放區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="68f3d-108">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="68f3d-109">如果不是後端伺服器的 Enterprise Edition 成員伺服器失敗，請參閱 [在 Lync server 2013 中還原 Enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="68f3d-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="68f3d-110">建議您先取得系統的影像複本，再開始還原。</span><span class="sxs-lookup"><span data-stu-id="68f3d-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="68f3d-111">您可以使用這個影像做為復原點，以防還原期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="68f3d-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="68f3d-112">在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="68f3d-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="68f3d-113">若要還原 Enterprise Edition 後端伺服器鏡像資料庫</span><span class="sxs-lookup"><span data-stu-id="68f3d-113">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="68f3d-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="68f3d-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="68f3d-115">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="68f3d-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68f3d-116">卸載鏡像。</span><span class="sxs-lookup"><span data-stu-id="68f3d-116">Uninstall mirroring.</span></span> <span data-ttu-id="68f3d-117">首先，輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="68f3d-117">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="68f3d-118">例如：</span><span class="sxs-lookup"><span data-stu-id="68f3d-118">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="68f3d-119">請對此伺服器上的所有資料庫類型執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="68f3d-119">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="68f3d-120">建立全新或新的伺服器，其具有相同的完整功能變數名稱 (FQDN)  (DB1.contoso.com) 作為失敗的電腦，安裝作業系統，然後還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="68f3d-120">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="68f3d-121">這台伺服器將會做為新的鏡像運作。</span><span class="sxs-lookup"><span data-stu-id="68f3d-121">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="68f3d-122">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入新伺服器。</span><span class="sxs-lookup"><span data-stu-id="68f3d-122">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="68f3d-123">安裝 SQL Server 2012 或 SQL Server 2008 R2，並保持實例名稱與失敗之前相同。</span><span class="sxs-lookup"><span data-stu-id="68f3d-123">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="68f3d-124">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="68f3d-124">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="68f3d-125">使用拓撲產生器來安裝鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="68f3d-125">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="68f3d-126">請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="68f3d-126">Perform the following:</span></span>
    
      - <span data-ttu-id="68f3d-127">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="68f3d-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="68f3d-128">以滑鼠右鍵按一下 [Lync Server 2013] 節點，按一下 [ **拓撲**]，然後按一下 [ **安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="68f3d-128">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="68f3d-129">遵循 [ **安裝資料庫** ] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="68f3d-129">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="68f3d-130">在 [ **建立資料庫** ] 頁面上，選取您要重新建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="68f3d-130">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="68f3d-131">依照嚮導執行，直到出現 [ **建立鏡像資料庫** ] 的提示。</span><span class="sxs-lookup"><span data-stu-id="68f3d-131">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="68f3d-132">選取您要安裝的資料庫並完成此程式。</span><span class="sxs-lookup"><span data-stu-id="68f3d-132">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="68f3d-133">您可以使用 <STRONG>Install-CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不是執行拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="68f3d-133">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="68f3d-134">如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。</span><span class="sxs-lookup"><span data-stu-id="68f3d-134">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

