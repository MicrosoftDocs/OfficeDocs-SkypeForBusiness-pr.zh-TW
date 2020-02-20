---
title: Lync Server 2013： 設定要監控的 Lync Server 電腦
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71188be470d6f2d561a068840c3cfee9e3e5ad9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="bd5fa-102">在 Lync Server 2013 中設定要監控的 Lync Server 電腦</span><span class="sxs-lookup"><span data-stu-id="bd5fa-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd5fa-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="bd5fa-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bd5fa-104">Lync Server 2013 不使用 Microsoft Lync Server 2010 中使用的集中探索程序，因為每個您想要監視的 Lync Server 2013 電腦必須能夠自我報告來管理伺服器其存在。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="bd5fa-105">若要將此位址設可能，您必須安裝 Operations Manager 代理程式檔案，在每個要監視的電腦上。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="bd5fa-106">在安裝代理程式檔案之後，您必須設定電腦，以作為 System Center proxy。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="bd5fa-107">請注意，這些程序應該執行後您已安裝並設定這些電腦上的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

