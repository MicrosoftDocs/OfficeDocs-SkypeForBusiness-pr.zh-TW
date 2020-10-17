---
title: Lync Server 2013：發行更新的拓撲
description: Lync Server 2013：發行更新的拓撲。
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
ms.openlocfilehash: c27cca2eae86eadaf1ff37e2c3520eaec3f86c98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571689"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="82de8-103">在 Lync Server 2013 中發佈更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="82de8-103">Publish the updated topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82de8-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="82de8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="82de8-105">在拓撲產生器中更新拓撲之後，您必須將拓撲發行至中央管理存放區，才能設定及使用 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="82de8-105">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="82de8-106">資料的唯讀複本會複寫到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="82de8-106">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="82de8-107">發行更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="82de8-107">To publish an updated topology</span></span>

<span data-ttu-id="82de8-108">在發佈拓撲之前，請安裝 Persistent Chat Server 的資料庫。</span><span class="sxs-lookup"><span data-stu-id="82de8-108">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="82de8-109">使用拓撲產生器，選取 [ **動作** ] 並 **安裝資料庫**以安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="82de8-109">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="82de8-110">在執行 Lync Server 2013 的電腦上，或安裝 Lync Server 系統管理工具的電腦上，使用 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組的成員帳戶進行登入。而且具有要用於 Persistent Chat Server 檔存放區之檔案存放區上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的任意自由訪問 (控制清單 (dacl) # A5，或具有同等使用者權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="82de8-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="82de8-111">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="82de8-111">Start Topology Builder.</span></span> <span data-ttu-id="82de8-112">選取 **[從現有的部署下載拓撲]**，若您已將拓撲儲存在本機上，可選取 **[從本機檔案開啟拓撲]**。</span><span class="sxs-lookup"><span data-stu-id="82de8-112">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="82de8-113">在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **發行拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="82de8-113">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="82de8-114">在 **[發行拓撲]** 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="82de8-114">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="82de8-115">在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="82de8-115">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="82de8-116">發行拓撲之後，您必須先設定 Persistent Chat Server 的支援，才能封存任何內容。</span><span class="sxs-lookup"><span data-stu-id="82de8-116">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

