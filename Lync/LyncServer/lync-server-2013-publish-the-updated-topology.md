---
title: Lync Server 2013： 發佈更新過的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589398c97a17f41f38394d5d3a57da4d3fec14ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="3cb09-102">在 Lync Server 2013 中發佈更新過的拓撲</span><span class="sxs-lookup"><span data-stu-id="3cb09-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cb09-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="3cb09-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3cb09-104">在更新之後您在拓撲產生器的拓撲，您必須中央管理存放區發行拓撲，您可以設定及使用 Persistent Chat Server 之前。</span><span class="sxs-lookup"><span data-stu-id="3cb09-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="3cb09-105">資料的唯讀複本會複寫到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="3cb09-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="3cb09-106">發行更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="3cb09-106">To publish an updated topology</span></span>

<span data-ttu-id="3cb09-107">發行拓撲之前，請安裝 Persistent Chat Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="3cb09-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="3cb09-108">使用拓撲產生器來選取**巨集指令**並**安裝資料庫**，來安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="3cb09-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="3cb09-109">找出是執行 Lync Server 2013 或在 Lync Server 系統管理工具安裝上使用為**Domain Admins**群組和**RTCUniversalServerAdmins**群組的成員帳戶登入和用於 Persistent Chat Server 檔案存放區 （以便拓撲產生器可以設定必要的判別存取控制清單 (Dacl)） 的檔案存放區上具有完整控制權限 （亦即，讀取、 寫入及修改） 的電腦上，或具有相等使用者權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3cb09-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="3cb09-110">啟動拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="3cb09-110">Start Topology Builder.</span></span> <span data-ttu-id="3cb09-111">選取 **[從現有的部署下載拓撲]**，若您已將拓撲儲存在本機上，可選取 **[從本機檔案開啟拓撲]**。</span><span class="sxs-lookup"><span data-stu-id="3cb09-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="3cb09-112">在主控台樹狀目錄中，以滑鼠右鍵按一下 [ **Lync Server 2013**中，，，然後按一下 [**發行拓撲**。</span><span class="sxs-lookup"><span data-stu-id="3cb09-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="3cb09-113">在 **[發行拓撲]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3cb09-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="3cb09-114">在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3cb09-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3cb09-115">發行拓撲之後, 您必須設定支援 for Persistent Chat Server 之前可以封存任何內容。</span><span class="sxs-lookup"><span data-stu-id="3cb09-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

