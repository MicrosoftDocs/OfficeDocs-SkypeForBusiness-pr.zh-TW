---
title: Lync Server 2013：在拓撲產生器中修改主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 001a94927d6160d138d344bf1a8fffcf519b58b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534390"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="e9d15-102">在 Lync Server 2013 中的拓撲產生器中修改主幹</span><span class="sxs-lookup"><span data-stu-id="e9d15-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d15-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e9d15-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e9d15-104">請依照下列步驟，修改主幹的替代媒體 IP 位址和替代旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="e9d15-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="e9d15-105">修改主幹的替代媒體 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9d15-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="e9d15-106">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e9d15-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9d15-107">執行 Set-CsPstnGateway Cmdlet，並修改 Lync Server 管理命令介面中的 [AlternateBypassId] 欄位。</span><span class="sxs-lookup"><span data-stu-id="e9d15-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="e9d15-108">修改主幹的替代 BypassID</span><span class="sxs-lookup"><span data-stu-id="e9d15-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="e9d15-109">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e9d15-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9d15-110">執行 Set-CsPstnGateway Cmdlet，並修改 Lync Server 管理命令介面中的 [AlternateBypassId] 欄位。</span><span class="sxs-lookup"><span data-stu-id="e9d15-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

