---
title: Lync Server 2013：發佈已更新的拓撲以新增封存資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f39e5f35dbd088543456f09ddd49f6aa2f9325c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="c9ad8-102">發佈已更新的拓撲，以便在 Lync Server 2013 中新增封存資料庫</span><span class="sxs-lookup"><span data-stu-id="c9ad8-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ad8-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c9ad8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c9ad8-104">在拓撲建立器中更新拓撲之後，您必須先將拓撲發佈到中央管理儲存體，才能設定及使用封存。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="c9ad8-105">唯讀複本會將資料複製到拓撲中的所有伺服器，以讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="c9ad8-106">發佈更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="c9ad8-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="c9ad8-107">在執行 Lync Server 2013 或已安裝 Lync Server 系統管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權利的帳戶）。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9ad8-108">您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將伺服器新增到拓撲中。您必須使用<STRONG>網域系統管理員</STRONG>群組和<STRONG>RTCUniversalServerAdmins</STRONG>群組成員的帳戶，且在您用於 Lync server 2013 檔案存放區之檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立員可以設定必要的隨機存取控制清單（dacl）或具有同等權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="c9ad8-109">使用拓撲建立器開啟您在前一節所建立的拓撲。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="c9ad8-110">在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="c9ad8-111">在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="c9ad8-112">在 [**建立資料庫**] 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9ad8-113">如果您沒有建立資料庫的適當許可權，您可以取消選取資料庫，且具有適當許可權的人員可以建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="c9ad8-114">如需有關所需系統管理員許可權和許可權的詳細資訊，請參閱部署檔中的<A href="lync-server-2013-deployment-permissions-for-sql-server.md">[在 Lync server 2013 中的 SQL Server 部署許可權</A>]。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c9ad8-115">只有專用 SQL Server 服務器上的資料庫才能使用拓撲建立器進行安裝。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="c9ad8-116">與其他伺服器元件 collocated 之 SQL Server 服務器上的資料庫，必須透過在該電腦上執行本機安裝程式來安裝。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="c9ad8-117">在 [**發佈嚮導完成]** 頁面上，確認拓撲已順利發佈，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c9ad8-118">發佈拓朴之後，您必須先設定用於封存的選項和原則，才能存檔任何內容。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="c9ad8-119">如需詳細資訊，請參閱在部署檔中設定<A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中的存檔支援</A>。</span><span class="sxs-lookup"><span data-stu-id="c9ad8-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

