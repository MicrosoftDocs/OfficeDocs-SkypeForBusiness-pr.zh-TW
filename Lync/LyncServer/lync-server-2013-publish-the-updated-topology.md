---
title: Lync Server 2013：發行更新後的拓撲
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
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="3de33-102">在 Lync Server 2013 中發行更新後的拓撲</span><span class="sxs-lookup"><span data-stu-id="3de33-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3de33-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3de33-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3de33-104">在拓撲建立器中更新拓撲之後，您必須先將拓撲發佈到中央管理儲存區，才能設定及使用持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="3de33-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="3de33-105">唯讀複本會將資料複製到拓撲中的所有伺服器，以讓所有伺服器與拓撲和其他設定變更保持同步。</span><span class="sxs-lookup"><span data-stu-id="3de33-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="3de33-106">發佈已更新的拓撲</span><span class="sxs-lookup"><span data-stu-id="3de33-106">To publish an updated topology</span></span>

<span data-ttu-id="3de33-107">在發佈拓撲前，請先安裝持久聊天伺服器的資料庫。</span><span class="sxs-lookup"><span data-stu-id="3de33-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="3de33-108">使用拓撲建立器，選取 [**動作**] 並**安裝資料庫**以安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="3de33-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="3de33-109">在執行 Lync Server 2013 或已安裝 Lync Server 管理工具的電腦上，使用 [**網域系統管理員**] 群組和 [ **RTCUniversalServerAdmins** ] 群組成員的帳戶登入，並在檔案存放區上擁有 [完全控制] 許可權（也就是讀取、寫入及修改），以用於持續聊天伺服器檔案存放區（以便讓拓撲產生器可以設定必要的隨機存取控制清單（dacl）），或是具有同等使用者權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="3de33-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="3de33-110">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="3de33-110">Start Topology Builder.</span></span> <span data-ttu-id="3de33-111">選取 [**從現有部署下載拓朴**]，或**從本機檔案中開啟拓撲**（如果您在本機上儲存）。</span><span class="sxs-lookup"><span data-stu-id="3de33-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="3de33-112">在主控台樹中，以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**發佈拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="3de33-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="3de33-113">在 [**發佈拓撲**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3de33-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="3de33-114">在 [**發佈嚮導完成]** 頁面上，確認拓撲已順利發佈，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3de33-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3de33-115">發佈拓朴之後，您必須先設定持久聊天伺服器的支援，才能封存任何內容。</span><span class="sxs-lookup"><span data-stu-id="3de33-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

