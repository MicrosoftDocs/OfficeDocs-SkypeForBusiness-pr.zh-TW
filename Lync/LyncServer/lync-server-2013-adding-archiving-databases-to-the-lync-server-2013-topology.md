---
title: Lync Server 2013：將存檔資料庫新增至 Lync Server 2013 拓撲結構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="ada3f-102">將存檔資料庫新增到 Lync Server 2013 拓撲</span><span class="sxs-lookup"><span data-stu-id="ada3f-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ada3f-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="ada3f-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="ada3f-104">您必須先將存檔納入拓撲中，才能設定您的部署支援封存。</span><span class="sxs-lookup"><span data-stu-id="ada3f-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="ada3f-105">本主題中的資訊說明如何使用拓撲建立器，將封存新增到您現有的拓撲。</span><span class="sxs-lookup"><span data-stu-id="ada3f-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ada3f-106">如果您想要使用 Microsoft Exchange 整合來在 Exchange 2013 伺服器上為您的部署中的所有使用者儲存封存資料和檔案，請勿指定<STRONG>[封存 Sql server store</STRONG> ] 或<STRONG>[使用 SQL Server store 鏡像</STRONG>資訊]。</span><span class="sxs-lookup"><span data-stu-id="ada3f-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="ada3f-107">將封存資料庫支援新增到您的拓撲</span><span class="sxs-lookup"><span data-stu-id="ada3f-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="ada3f-108">在執行 Lync Server 2013 或安裝 Lync Server 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或具有同等使用者權限的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="ada3f-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ada3f-109">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將伺服器新增到拓撲中。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您用於 Lync server 2013 檔案存放區之檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立員可以設定必要的隨機存取控制清單（dacl）或具有同等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ada3f-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="ada3f-110">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="ada3f-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="ada3f-111">在主控台樹中，流覽至您要在其中部署封存的 [前端] 池，然後按一下您要部署封存的 [前端] 池名稱。</span><span class="sxs-lookup"><span data-stu-id="ada3f-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="ada3f-112">在 [**動作**] 功能表中，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ada3f-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="ada3f-113">在 [**編輯屬性**] 對話方塊中，按一下 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="ada3f-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="ada3f-114">**向下滾動至 [** 封存]。</span><span class="sxs-lookup"><span data-stu-id="ada3f-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="ada3f-115">選取 [**存檔**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ada3f-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="ada3f-116">在 **[封存 SQL Server store** ] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ada3f-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="ada3f-117">若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ada3f-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="ada3f-118">如果您的所有使用者都是以 Microsoft Exchange Server 2013 或更高版本為宿主，您可以在 Exchange 中將所有使用者的 Lync 通訊封存。</span><span class="sxs-lookup"><span data-stu-id="ada3f-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="ada3f-119">在這種情況下，您不需要設定 SQL Server 封存存放區。</span><span class="sxs-lookup"><span data-stu-id="ada3f-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="ada3f-120">若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ada3f-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="ada3f-121">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ada3f-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="ada3f-122">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="ada3f-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="ada3f-123">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ada3f-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="ada3f-124">如果您想要使用 SQL Server store 鏡像，請選取 **[啟用 Sql Server store 鏡像**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ada3f-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="ada3f-125">若要使用現有的 SQL Server store 進行鏡像，請在 [封存**Sql server store** ] 下拉式清單方塊中，按一下您要用來進行鏡像的 SQL Server store 名稱。</span><span class="sxs-lookup"><span data-stu-id="ada3f-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="ada3f-126">若要指定新的 SQL Server 存放區以進行鏡像，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ada3f-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="ada3f-127">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ada3f-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="ada3f-128">按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。</span><span class="sxs-lookup"><span data-stu-id="ada3f-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="ada3f-129">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ada3f-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="ada3f-130">如果您啟用 SQL Server 鏡像，且想要包含 SQL Server 鏡像見證（第三個獨立的 SQL Server 實例，可偵測主要 SQL Server 服務器與鏡像實例的健康情況），請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ada3f-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="ada3f-131">在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ada3f-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="ada3f-132">按一下 [**預設實例**] 以使用預設實例，或按一下 [指定**實例**]，然後指定您要用於鏡像見證的實例。</span><span class="sxs-lookup"><span data-stu-id="ada3f-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="ada3f-133">如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="ada3f-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="ada3f-134">若要儲存配置，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ada3f-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

