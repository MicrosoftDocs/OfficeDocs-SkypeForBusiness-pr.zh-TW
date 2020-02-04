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
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="550ed-102">移轉類比裝置</span><span class="sxs-lookup"><span data-stu-id="550ed-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="550ed-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="550ed-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="550ed-104">Lync Server 提供模擬裝置的支援。</span><span class="sxs-lookup"><span data-stu-id="550ed-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="550ed-105">具體說來，支援的類比裝置是類比音訊電話和類比傳真電腦。</span><span class="sxs-lookup"><span data-stu-id="550ed-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="550ed-106">您可以設定合格的閘道，以支援 Lync Server 環境中的類比裝置使用。</span><span class="sxs-lookup"><span data-stu-id="550ed-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="550ed-107">從 Lync Server 2010 遷移至 Lync Server 2013 之後，您也必須遷移與類比裝置相關聯的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="550ed-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="550ed-108">使用 Lync Server 管理命令介面，先檢索與 Lync Server 2010 類比裝置相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="550ed-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="550ed-109">遷移類比裝置</span><span class="sxs-lookup"><span data-stu-id="550ed-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="550ed-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="550ed-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="550ed-111">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="550ed-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="550ed-112">確認所有連絡人物件都已移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="550ed-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="550ed-113">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="550ed-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="550ed-114">確認所有連絡人物件現在都已與 Lync Server 2013 池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="550ed-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

