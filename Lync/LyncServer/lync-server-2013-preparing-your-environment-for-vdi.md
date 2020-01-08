---
title: Lync Server 2013：針對 VDI 準備環境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5081d1267b9de521ebd17fa5f3ec5ae57a912970
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="3cc8d-102">針對 VDI 準備 Lync Server 2013 環境</span><span class="sxs-lookup"><span data-stu-id="3cc8d-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc8d-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3cc8d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3cc8d-104">若要為 Lync VDI 外掛程式準備環境，系統管理員必須執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="3cc8d-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="3cc8d-105">在 Lync Server 2013 中，確保所有 VDI 使用者的 EnableMediaRedirection 都設定為 TRUE。</span><span class="sxs-lookup"><span data-stu-id="3cc8d-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="3cc8d-106">如需詳細資訊，請參閱[新版 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 和[CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="3cc8d-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="3cc8d-107">在資料中心電腦上，在所有虛擬機器上安裝 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3cc8d-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="3cc8d-108">在本機電腦上，安裝 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="3cc8d-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

