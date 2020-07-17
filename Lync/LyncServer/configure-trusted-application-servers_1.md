---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="74697-102">設定信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="74697-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74697-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="74697-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="74697-104">在混合式環境中，如果您在將舊版 Office 通訊伺服器拓撲與 Lync Server 2013 合併之後建立新的信任應用程式伺服器，並使用拓撲產生器來定義新的信任應用程式伺服器，則必須將下一個躍點集區設定為 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="74697-104">In a mixed environment, if you create a new trusted application server after merging the legacy Office Communications Server topology with Lync Server 2013, and you define a new trusted application server using Topology Builder, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="74697-105">在合併環境中，舊版 Office 通訊伺服器集區和 Lync Server 2013 集區會出現在下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="74697-105">In a merged environment, both the legacy Office Communications Server pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="74697-106">但不\*\* 支援選取舊版集區。</span><span class="sxs-lookup"><span data-stu-id="74697-106">Selecting the legacy pool is *not* supported.</span></span>

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="74697-107">在建立信任的應用程式伺服器時，選取 [Lync Server 2013] 做為下一個躍點</span><span class="sxs-lookup"><span data-stu-id="74697-107">To select Lync Server 2013 as next hop when creating a Trusted application server</span></span>

1.  <span data-ttu-id="74697-108">在拓樸產生器中開啟現有的拓樸。</span><span class="sxs-lookup"><span data-stu-id="74697-108">Open an existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="74697-109">在左側窗格中，用滑鼠右鍵按一下 **[信任的應用程式伺服器]**，然後按一下 **[新增信任的應用程式集區]**。</span><span class="sxs-lookup"><span data-stu-id="74697-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="74697-110">輸入信任的應用程式集區的 **[集區 FQDN]**，然後選取是否成為單一伺服器或多重伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="74697-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server deployment.</span></span>

4.  <span data-ttu-id="74697-111">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="74697-111">Click **Next**.</span></span>

5.  <span data-ttu-id="74697-112">在 [**選取下一個躍點]** 頁面上，從清單中選取 [Lync Server 2013 前端集區]。</span><span class="sxs-lookup"><span data-stu-id="74697-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>
    
    <span data-ttu-id="74697-113">![[定義新的信任的應用程式集區] 對話方塊](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "[定義新的信任的應用程式集區] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="74697-113">![Define New Trusted Application Pool dialog](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Define New Trusted Application Pool dialog")</span></span>  

6.  <span data-ttu-id="74697-114">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="74697-114">Click **Finish**.</span></span>

7.  <span data-ttu-id="74697-115">選取頂端節點 **[Lync Server]**，然後從 **[動作]** 窗格中選取 **[發行]**。</span><span class="sxs-lookup"><span data-stu-id="74697-115">Select the top node **Lync Server** and from the **Actions** pane, select **Publish**.</span></span>

8.  <span data-ttu-id="74697-116">確認 **[信任的應用程式集區]** 已成功建立，並與正確的前端集區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="74697-116">Verify the **Trusted Application Pool** was created successfully and is associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

