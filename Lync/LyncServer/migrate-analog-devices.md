---
title: 移轉類比裝置
description: 遷移類比裝置。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579399"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="c987e-103">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="c987e-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c987e-104">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c987e-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c987e-105">Lync Server 提供類比裝置的支援。</span><span class="sxs-lookup"><span data-stu-id="c987e-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="c987e-106">具體而言，支援的類比裝置為類比語音電話與類比傳真機。</span><span class="sxs-lookup"><span data-stu-id="c987e-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="c987e-107">您可以設定合格的閘道，以支援在 Lync Server 環境中使用類比裝置。</span><span class="sxs-lookup"><span data-stu-id="c987e-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="c987e-108">從 Lync Server 2010 遷移至 Lync Server 2013 之後，您也必須遷移與類比裝置相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="c987e-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="c987e-109">使用 Lync Server 管理命令介面，先找回 Lync Server 2010 類比裝置相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="c987e-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="c987e-110">遷移類比裝置</span><span class="sxs-lookup"><span data-stu-id="c987e-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="c987e-111">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c987e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c987e-112">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="c987e-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="c987e-113">確認已將所有連絡人物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="c987e-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c987e-114">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="c987e-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="c987e-115">確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="c987e-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

