---
title: Lync Server 2013：選取中央管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef3cff58600697f64b64860f37a7daab8ebfc8f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510420"
---
# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="1b3fa-102">在 Lync Server 2013 中選取中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="1b3fa-102">Select the Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b3fa-103">_**主題上次修改日期：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="1b3fa-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="1b3fa-104">在定義及設定拓撲之前，您必須先定義安裝中央管理伺服器的位置。</span><span class="sxs-lookup"><span data-stu-id="1b3fa-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b3fa-105">除非您已在拓撲產生器中發佈拓撲，否則此項不會生效。</span><span class="sxs-lookup"><span data-stu-id="1b3fa-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="1b3fa-106">若要在建立及發行拓撲之前設定中央管理伺服器，請執行 <STRONG>remove-csconfigurationstorelocation</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="1b3fa-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="1b3fa-107">若要選取中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="1b3fa-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="1b3fa-108">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="1b3fa-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="1b3fa-109">在 [Lync Server 2013] 節點上按一下滑鼠右鍵，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1b3fa-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="1b3fa-110">在 [中央管理伺服器] 窗格中，選取要在其上安裝中央管理伺服器的前端伺服器，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1b3fa-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

