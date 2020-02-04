---
title: Lync Server 2013：在拓撲建立器中修改主幹
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
ms.openlocfilehash: 3e1c603aa24a0d31ea87178f740f824ae77f20f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="adc0f-102">在 Lync Server 2013 的拓撲產生器中修改主幹</span><span class="sxs-lookup"><span data-stu-id="adc0f-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adc0f-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="adc0f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="adc0f-104">請依照下列步驟來修改主幹的替代媒體 IP 位址和替代旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="adc0f-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="adc0f-105">修改主幹的備用媒體 IP 位址</span><span class="sxs-lookup"><span data-stu-id="adc0f-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="adc0f-106">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="adc0f-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="adc0f-107">執行 CsPstnGateway Cmdlet，然後在 Lync Server Management Shell 中修改 AlternateBypassId 欄位。</span><span class="sxs-lookup"><span data-stu-id="adc0f-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="adc0f-108">修改主幹的替代 BypassID</span><span class="sxs-lookup"><span data-stu-id="adc0f-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="adc0f-109">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="adc0f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="adc0f-110">執行 CsPstnGateway Cmdlet，然後在 Lync Server Management Shell 中修改 AlternateBypassId 欄位。</span><span class="sxs-lookup"><span data-stu-id="adc0f-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

