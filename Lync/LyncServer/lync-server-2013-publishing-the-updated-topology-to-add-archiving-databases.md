---
title: Lync Server 2013：發佈更新的拓撲以新增封存資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5834c6c7d0386f7943c523a184ea63f8ba129a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512240"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="4c578-102">發佈已更新的拓撲，以在 Lync Server 2013 中新增封存資料庫</span><span class="sxs-lookup"><span data-stu-id="4c578-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c578-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4c578-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4c578-104">在拓撲產生器中更新拓撲之後，您必須將拓撲發佈至中央管理存放區，才能設定及使用封存。</span><span class="sxs-lookup"><span data-stu-id="4c578-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="4c578-105">資料的唯讀複本會複製到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="4c578-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="4c578-106">發行更新的拓樸</span><span class="sxs-lookup"><span data-stu-id="4c578-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="4c578-107">在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4c578-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c578-108">您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將伺服器新增至拓撲），則必須使用屬於 <STRONG>Domain Admins</STRONG> 群組和 <STRONG>RTCUniversalServerAdmins</STRONG> 群組成員的帳戶。而且具有在您用於 Lync server 2013 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的自由存取控制清單 (dacl) ，或具有同等 (權利的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4c578-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="4c578-109">使用拓撲產生器開啟您在上一節中建立的拓撲。</span><span class="sxs-lookup"><span data-stu-id="4c578-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="4c578-110">在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="4c578-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="4c578-111">在 **[發行拓樸]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4c578-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="4c578-112">在 **[建立資料庫]** 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4c578-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4c578-113">如果您未具備建立資料庫的適當權限，可以取消選取資料庫，讓具備適當權限的人能夠建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="4c578-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="4c578-114">如需有關必要系統管理員權力與許可權的詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">SQL Server 的部署許可權（Lync server 2013</A> ）。</span><span class="sxs-lookup"><span data-stu-id="4c578-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="4c578-115">只有專用 SQL Server 服務器上的資料庫才能使用拓撲產生器進行安裝。</span><span class="sxs-lookup"><span data-stu-id="4c578-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="4c578-116">與其他伺服器元件組合的 SQL Server 服務器上的資料庫，必須透過在該電腦上執行本機安裝程式來安裝。</span><span class="sxs-lookup"><span data-stu-id="4c578-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="4c578-117">在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4c578-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4c578-118">發行拓樸之後，您必須先為封存設定選項和原則，才能封存內容。</span><span class="sxs-lookup"><span data-stu-id="4c578-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="4c578-119">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013</A> 中設定封存支援。</span><span class="sxs-lookup"><span data-stu-id="4c578-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

