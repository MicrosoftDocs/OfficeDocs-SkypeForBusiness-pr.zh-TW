---
title: Lync Server 2013：查看共同區域電話資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b9a928925bfc3ff933e2d94d39db8b652e6ff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="c5496-102">在 Lync Server 2013 中查看共同區域電話資訊</span><span class="sxs-lookup"><span data-stu-id="c5496-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5496-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="c5496-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="c5496-104">您可以使用**Get-CsCommonAreaPhone** Cmdlet，查看設定供組織使用之公用區域電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c5496-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="c5496-105">使用無任何參數時，此 Cmdlet 會傳回所有公用區域電話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c5496-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="c5496-106">選用參數提供不同的篩選資訊的方式。</span><span class="sxs-lookup"><span data-stu-id="c5496-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="c5496-107">例如，您可以傳回在指定的組織單位 (OU) 或所有位於指定大樓中的連絡人物件中，都有 contact 物件的所有公共區域電話。</span><span class="sxs-lookup"><span data-stu-id="c5496-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="c5496-108">如需**Get-CsCommonAreaPhone**參數的詳細資訊，請參閱[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="c5496-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="c5496-109">請從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行**Get-CsCommonAreaPhone** 。</span><span class="sxs-lookup"><span data-stu-id="c5496-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="c5496-110">查看您所有通用區域電話的資訊</span><span class="sxs-lookup"><span data-stu-id="c5496-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="c5496-111">若要查看所有通用區域電話的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="c5496-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="c5496-112">您會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="c5496-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="c5496-113">如需詳細資訊，請參閱[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="c5496-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

