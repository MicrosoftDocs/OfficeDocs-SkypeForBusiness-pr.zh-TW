---
title: 移轉類比裝置
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
ms.openlocfilehash: 70e756fdaa49fc4c825a2c8548eb2c7f2e4acab2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="891f3-102">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="891f3-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="891f3-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="891f3-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="891f3-104">Lync Server 提供類比裝置的支援。</span><span class="sxs-lookup"><span data-stu-id="891f3-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="891f3-105">具體而言，支援的類比裝置為類比語音電話與類比傳真機。</span><span class="sxs-lookup"><span data-stu-id="891f3-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="891f3-106">您可以設定合格的閘道，以支援在 Lync Server 環境中使用類比裝置。</span><span class="sxs-lookup"><span data-stu-id="891f3-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="891f3-107">從 Lync Server 2010 遷移至 Lync Server 2013 之後，您也必須遷移與類比裝置相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="891f3-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="891f3-108">使用 Lync Server 管理命令介面，先找回 Lync Server 2010 類比裝置相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="891f3-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="891f3-109">遷移類比裝置</span><span class="sxs-lookup"><span data-stu-id="891f3-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="891f3-110">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="891f3-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="891f3-111">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="891f3-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="891f3-112">確認已將所有連絡人物件移至 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="891f3-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="891f3-113">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="891f3-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="891f3-114">確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="891f3-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

