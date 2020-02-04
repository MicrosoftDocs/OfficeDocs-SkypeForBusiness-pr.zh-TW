---
title: 還原鏡像企業版後端伺服器-鏡像
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
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="defc5-102">在 Lync Server 2013 中還原鏡像企業版後端伺服器-鏡像</span><span class="sxs-lookup"><span data-stu-id="defc5-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="defc5-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="defc5-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="defc5-104">如果您在鏡像設定中有企業版後端伺服器，而且只有鏡像失敗，請遵循本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="defc5-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="defc5-105">如果主資料庫和鏡像都未通過，請參閱[在 Lync Server 2013 中還原企業版後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。</span><span class="sxs-lookup"><span data-stu-id="defc5-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="defc5-106">如果只有主要失敗，請參閱[在 Lync Server 2013 中還原鏡像企業版後端伺服器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。</span><span class="sxs-lookup"><span data-stu-id="defc5-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="defc5-107">如果裝載中央管理儲存區的資料庫失敗，請參閱[在 Lync server 2013 中還原託管中央管理儲存區的伺服器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。</span><span class="sxs-lookup"><span data-stu-id="defc5-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="defc5-108">如果不是後端伺服器的企業版成員伺服器失敗，請參閱[在 Lync server 2013 中還原企業版成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="defc5-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="defc5-109">我們建議您先取得系統的影像複本，然後再開始還原。</span><span class="sxs-lookup"><span data-stu-id="defc5-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="defc5-110">您可以使用這個影像做為復原點，以防還原期間發生的問題。</span><span class="sxs-lookup"><span data-stu-id="defc5-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="defc5-111">您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="defc5-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="defc5-112">若要還原企業版後端伺服器鏡像資料庫</span><span class="sxs-lookup"><span data-stu-id="defc5-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="defc5-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="defc5-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="defc5-114">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="defc5-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="defc5-115">卸載鏡像。</span><span class="sxs-lookup"><span data-stu-id="defc5-115">Uninstall mirroring.</span></span> <span data-ttu-id="defc5-116">首先，請輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="defc5-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="defc5-117">例如：</span><span class="sxs-lookup"><span data-stu-id="defc5-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="defc5-118">針對此伺服器上的所有資料庫類型執行此動作。</span><span class="sxs-lookup"><span data-stu-id="defc5-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="defc5-119">建立乾淨或新伺服器，其具有與失敗的電腦相同的完整功能變數名稱（FQDN）（DB1.contoso.com），安裝作業系統，然後還原或重新註冊證書。</span><span class="sxs-lookup"><span data-stu-id="defc5-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="defc5-120">這個伺服器將做為新的鏡像。</span><span class="sxs-lookup"><span data-stu-id="defc5-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="defc5-121">從屬於 [RTCUniversalServerAdmins] 群組成員的使用者帳戶登入新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="defc5-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="defc5-122">安裝 SQL Server 2012 或 SQL Server 2008 R2，讓實例名稱保持與失敗前相同。</span><span class="sxs-lookup"><span data-stu-id="defc5-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="defc5-123">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="defc5-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="defc5-124">使用拓撲建立器來安裝鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="defc5-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="defc5-125">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="defc5-125">Perform the following:</span></span>
    
      - <span data-ttu-id="defc5-126">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="defc5-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="defc5-127">以滑鼠右鍵按一下 Lync Server 2013 節點，按一下 [**拓撲圖**]，然後按一下 [**安裝資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="defc5-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="defc5-128">遵循 [**安裝資料庫**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="defc5-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="defc5-129">在 [**建立資料庫**] 頁面上，選取您要重新建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="defc5-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="defc5-130">遵循嚮導，直到出現 [**建立鏡像資料庫**] 的提示。</span><span class="sxs-lookup"><span data-stu-id="defc5-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="defc5-131">選取您要安裝的資料庫，並完成這個程式。</span><span class="sxs-lookup"><span data-stu-id="defc5-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="defc5-132">您可以使用<STRONG>CsMirrorDatabase</STRONG> Cmdlet 來設定鏡像，而不是執行拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="defc5-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="defc5-133">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="defc5-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

