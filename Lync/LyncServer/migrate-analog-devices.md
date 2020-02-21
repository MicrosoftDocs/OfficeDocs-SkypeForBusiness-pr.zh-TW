---
title: 移轉類比裝置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc1c3420c22f4cc58bd0e617fd9ba98e16102c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="cf39d-102">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="cf39d-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf39d-103">_**主題上次修改日期：** 2012 年 10-16_</span><span class="sxs-lookup"><span data-stu-id="cf39d-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="cf39d-104">Lync Server 的類比裝置提供支援。</span><span class="sxs-lookup"><span data-stu-id="cf39d-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="cf39d-105">具體而言，支援的類比裝置為類比語音電話與類比傳真機。</span><span class="sxs-lookup"><span data-stu-id="cf39d-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="cf39d-106">您可以設定 Lync Server 環境中支援的類比裝置使用完整的閘道。</span><span class="sxs-lookup"><span data-stu-id="cf39d-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="cf39d-107">從 Lync Server 2010 移轉至 Lync Server 2013 之後，您也必須移轉相關聯的類比裝置連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="cf39d-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="cf39d-108">使用 Lync Server 管理命令介面來第一次擷取與 Lync Server 2010 類比裝置，相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="cf39d-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="cf39d-109">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="cf39d-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="cf39d-110">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="cf39d-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cf39d-111">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="cf39d-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="cf39d-112">確認所有連絡人物件已被移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="cf39d-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="cf39d-113">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="cf39d-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="cf39d-114">確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="cf39d-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

