---
title: Lync Server 2013：設定受監視的 Lync Server 電腦
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a5d252035820f373183d1927b322a929340716
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="c96a0-102">設定將在 Lync Server 2013 中監視的 Lync Server 電腦</span><span class="sxs-lookup"><span data-stu-id="c96a0-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c96a0-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c96a0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c96a0-104">由於 Lync Server 2013 未使用 Microsoft Lync Server 2010 中所用的中央探索程式，因此您要監視的每個 Lync Server 2013 電腦都必須能夠自行向管理伺服器自行報告現有的功能。</span><span class="sxs-lookup"><span data-stu-id="c96a0-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="c96a0-105">若要這樣做，您必須在每個要監視的電腦上安裝 Operations Manager 代理檔案。</span><span class="sxs-lookup"><span data-stu-id="c96a0-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="c96a0-106">安裝完代理程式檔案之後，您必須將電腦設定為系統中心 proxy。</span><span class="sxs-lookup"><span data-stu-id="c96a0-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="c96a0-107">請注意，當您在這些電腦上安裝和設定 Lync Server 之後，這些程式應該會執行。</span><span class="sxs-lookup"><span data-stu-id="c96a0-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

